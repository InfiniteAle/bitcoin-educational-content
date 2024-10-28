```
nume: LAPP bitcoin
descriere: Tutorial pentru a dezvolta prima ta LApp
---

Învață să programezi prima ta aplicație lightning

Cerințe:

- NodeJs >= 8
- LND >= 9

NodeJs poate fi descărcat de pe site-ul oficial

În loc să descărcăm și să configurăm un nod LND, vom folosi uneltele polar, care va efectua această sarcină pentru noi.

Pentru a construi aplicația noastră Lightning, vom folosi următoarele tehnologii:

- Express pentru serverul nostru web
- Șabloane Pug + bootstrap pentru frontend-ul nostru

## Sistem de operare

Se recomandă utilizarea Linux, dacă ești pe Windows 10 poți avea o consolă Linux urmând acești câțiva pași.
Pregătirea bazei

Folosește uneltele de generare a aplicațiilor, express, pentru a crea rapid un schelet de aplicație.

```
$ sudo npm install express-generator -g
```

Cu următoarea instrucțiune, creăm o aplicație Express numită lnapp. Aplicația va fi creată într-un director numit lnapp în directorul de lucru curent, iar motorul de vizualizare va fi atribuit lui Pug.

```
$ express --view=pug lnapp
```

Apoi intrăm în director și instalăm pachetele necesare pentru ca serverul web să funcționeze.

```
$ cd myapp
$ npm install
```

Acum pur și simplu rulăm serverul

```
$ npm start
```

În continuare, mergi la această adresă http://localhost:3000 în browser pentru a accesa aplicația.

Aplicația generată are următoarea structură de directoare:

```
.
├── app.js
├── bin
│ └── www
├── package.json
├── public
│ ├── images
│ ├── javascripts
│ └── stylesheets
│ └── style.css
├── routes
│ ├── index.js
│ └── users.js
└── views
├── error.pug
├── index.pug
└── layout.pug
```

## Polar

Descarcă Polar, instalează-l și creează o rețea cu 2 noduri LND (Alice și Bob) și 1 bitcoind. Odată ce vedem graficul în aplicație arătând nodurile noastre, apasă pe butonul Start și așteaptă câteva secunde până când indicatorul fiecărui nod își schimbă culoarea în verde.

Pentru a trimite plăți pe Lightning, este necesar ca nodurile să fie interconectate prin canale. Crearea canalelor cu Polar este foarte simplă, trebuie doar să facem clic cu mouse-ul pe una dintre urechile nodului Alice și să o tragem către una dintre urechile nodului Bob. Imediat, o fereastră modală intitulată Deschide canal nou ar trebui să apară, lăsăm valorile implicite și apăsăm butonul de deschidere canal. Acum repetăm acțiunea dar de data aceasta de la Bob la Alice, astfel ambele noduri pot trimite și primi bani.

## Nodemon

Pentru a evita să trebuiască să repornim nodejs de fiecare dată când facem o modificare în cod, vom instala nodemon

```
$ npm install nodemon -D
```

Trebuie să creăm o intrare în secțiunea de scripturi a fișierului package.json, adaugă această linie "dev": "nodemon ./bin/www", secțiunea de scripturi ar trebui să arate astfel:

```
"scripts": {
"start": "node ./bin/www",
"dev": "nodemon ./bin/www"
},
```

Mergi la consola unde rulează npm start, apasă ctrl + c și pornește nodejs din nou dar de data aceasta folosind nodemon

```
$ npm run dev
```

## Conectarea la LND

Pentru a ne conecta la un nod Lightning din nodejs, vom folosi biblioteca ln-service, vom instala de asemenea dotenv pentru a gestiona variabilele de mediu.

```
$ npm install ln-service dotenv
```
În directorul nostru lnapp, creează un fișier numit .env, acesta ar trebui să conțină următoarele variabile:

```
LND_GRPC_HOST=''
LND_CERT_BASE64=''
LND_MACAROON_BASE64=''
```

Întoarce-te la Polar, selectează Bob, nodul la care dorim să ne conectăm, mergi la tab-ul "Connect", copiază conținutul GRPC Host și plasează-l în variabila LND_GRPC_HOST, în partea de jos a tab-ului de conectare selectează base64 și copiază conținutul TLS Cert și plasează-l în variabila LND_CERT_BASE64, și fă același lucru cu macaroon-ul de admin în LND_MACAROON_BASE64.

Acum adaugă această linie în fișierul app.js situat în rădăcina directorului de lucru, trebuie să o copiem pe prima linie a fișierului.

```
require('dotenv').config();
```

Pentru a verifica că nodejs se poate conecta la nodul nostru, deschide fișierul routes/index.js, acest fișier de rute a fost creat de generatorul express, mai întâi necesităm biblioteca ln-service, așa că o adăugăm pe prima linie

```
const lnservice = require('ln-service');
```

Adăugăm o nouă rută care ne va oferi informații despre nodul nostru.

```
router.get('/info', async function(req, res, next) {
try {
// autentificare cu lnd
const { lnd } = lnservice.authenticatedLndGrpc({
cert: process.env.LND_CERT_BASE64,
macaroon: process.env.LND_MACAROON_BASE64,
socket: process.env.LND_GRPC_HOST,
});
// obține informații despre nod
const info = await lnservice.getWalletInfo({ lnd });

    // afișează info în format json
    res.send(`
      <h1>Informații nod</h1>
      <pre>${JSON.stringify(info, null, 2)}</pre>
    `);
    next();

} catch (e) {
console.log(e);
}
});
```

Acum mergi la această adresă http://localhost:3000/info

Dacă vezi un json cu informațiile nodului LND, felicitări!!! aplicația ta poate acum să interacționeze cu Lightning Network.
Crearea unui model fals

Pentru a simula o bază de date, trebuie să creăm un model fals, acest lucru ne va permite să folosim aplicația fără a instala și configura o bază de date.

Mai întâi, instalează pachetul uuid

```
$ npm install uuid
```

Creează directorul models și în interiorul acestuia, creează fișierul Post.js cu următorul conținut:

```
const { v4: uuidv4 } = require('uuid');'
class Post {
  constructor() {
    this.posts = [];
  }
  add({ time, name, content, paid, hash, preimage, request }) {
    const post = {
      id: uuidv4(),
      time: time || new Date(),
      name,
      content,
      paid: paid || false,
      hash: hash || null,
      preimage: preimage || null,
      request: request || null,
    };
    this.posts.push(post);

    return post;
  }

  find(id) {
    return this.posts.find(p => p.id === id);
  }

  findByHash(hash) {
    return this.posts.find(p => p.hash === hash);
  }

  findAll() {
    return this.posts;
  }

  findAllPaid() {
    return this.posts
      .filter(p => !!p.paid)
      .sort((a, b) => b.time - a.time);
  }

  paid(hash) {
    let updatedPost;
    this.posts = this.posts.map(p => {
      if (p.hash === hash) {
```markdown
const router = express.Router();
const posts = require('../models/posts');

router.post('/post', async (req, res) => {
  try {
    const { name, content } = req.body;
    const newPost = await posts.addPost({ name, content });
    if (newPost) {
      res.json({ success: true, data: newPost });
    } else {
      res.json({ success: false });
    }
  } catch (error) {
    res.status(500).send(error.toString());
  }
});

module.exports = router;
```

## Pregătirea interfeței

Avem nevoie de bootstrap pentru a face ca html-ul nostru să arate mai bine, așa că modificăm fișierul layout.pug situat în directorul views astfel:

```
doctype html
html
  head
    title= title
    link(rel='stylesheet', href='https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css')
    link(rel='stylesheet', href='/stylesheets/style.css')
  body
    block content
    block scripts
      script(src="https://code.jquery.com/jquery-3.4.1.min.js")
      script(src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js")
      script(src="/javascripts/main.js")
```

## Crearea unui Post

Pentru a crea un post, avem nevoie de un formular. În interiorul directorului views, creați un fișier numit form.pug cu următorul conținut:

```
.collapse#post-form
  form
    h2 Scrieți un articol
    .form-group
      label(for="name") Nume
      input(id="name").form-control
    .form-group
      label(for="content") Conținut
      textarea(id="content").form-control
    button.btn.btn-primary#send-btn(type="button") Trimite
```

## Javascript în frontend

Cel mai direct mod prin care putem interacționa cu utilizatorul este folosind javascript în browserul web. Pentru aceasta, creați un fișier numit main.js în directorul javascript, pe care îl apelăm deja din layout.pug. În acest fișier, inițializați proiectul. Conținutul inițial al main.js este următorul:

```
const App = {
  endpoint: 'http://localhost:3000/api',
  interval: null,
};

App.init = () => {
  $('#post-form').collapse('show');
  $('#send-btn').click(App.sendBtn);
}

App.sendBtn = () => {
  console.log('!hola');
};

$(() => App.init());
```

Apăsați butonul "Trimite" și dacă totul este în regulă, ar trebui să afișeze un mesaj "!hola" în consolă. Acum putem modifica metoda App.sendBtn() pentru a trimite informațiile către API-ul nostru.

```
App.sendBtn = async () => {
  const name = $('#name').val();
  const content = $('#content').val();
  const response = await App.makeRequest({
    api: "post",
    post: { name, content },
  });
  if (!response) console.error('Eroare la obținerea datelor!');
  if (response.success) {
    // Faceți ceva cu răspunsul
  }
};
```

```markdown
// Afișați în consolă datele care vin de la API
console.log(response.data);
}
};
```

De asemenea, creăm metoda App.makeRequest() și o adăugăm în main.js

```markdown
App.makeRequest = ({api, post}) => {
const type = !post ? 'GET' : 'POST';
const data = !!post ? JSON.stringify(post) : null;
return $.ajax(`${App.endpoint}/${api}`, {
type,
data,
contentType: 'application/json',
dataType: 'json',
});
};
```

## Crearea API-ului

Pentru a face acest lucru, trebuie să creăm un fișier nou în routes/api.js și să scriem metoda care răspunde la solicitarea făcută în cadrul App.sendBtn().

```markdown
const express = require('express');
```
```markdown
const lnservice = require('ln-service'); const router = express.Router();
const post = require('../models/Post');

router.post('/post', (req, res) => {
const { name, content } = req.body;
return res.json({
success: true,
data: { name, content },
});
});

module.exports = router;
```

Acest fișier trebuie inclus în app.js, așa că adăugăm aceste linii:

```markdown
const apiRouter = require('./routes/api');
app.use('/api', apiRouter);
```

Să apăsăm din nou butonul de trimitere și ar trebui să răspundă cu aceleași date pe care le-am introdus în formular.

## Crearea facturii

Metoda care este executată când un utilizator creează o postare ar trebui să genereze o factură, apoi să creeze un înregistrare în baza de date legând-o de factură și să returneze factura utilizatorului pentru a o putea plăti.

```markdown
router.post('/post', async (req, res) => {
// Autentificare cu lnd
const { lnd } = lnservice.authenticatedLndGrpc({
cert: process.env.LND_CERT_BASE64,
macaroon: process.env.LND_MACAROON_BASE64,
socket: process.env.LND_GRPC_HOST,
});

const { name, content } = req.body;
încercați {
const invoice = await lnservice.createInvoice({
lnd,
tokens: 1000,
description: name,
});
if (!!invoice) {
const p = post.add({
name,
content,
hash: invoice.id,
request: invoice.request,
preimage: invoice.secret,
});
return res.json({
success: true,
data: p,
});
}
} catch (e) {
console.log(e);
}
});
```

Dacă primim un obiect post ca răspuns după apăsarea butonului de trimitere, ca acesta, totul a mers corect. Acum trebuie să afișăm textul astfel încât utilizatorul să îl poată plăti.

```markdown
{
"success":true,
"data":{
"id":"0fb1544a-d7f9-487d-961a-d0004ecc515c",
"time":"2020-09-02T21:29:53.747Z",
"name":"epale",
"content":"contenido bla bla",
"paid":false,
"hash":"0e3c7a1151d8f8f202bc7264db83e554c9009f9bd32c0fcb0412772b310b520e",
"preimage":null,
}
```

## Noua vizualizare a facturii

În directorul views, trebuie să creăm un fișier numit invoice.pug cu următorul conținut:

```
.collapse#invoice-form
form
.h2 Plătește această factură
.form-group
textarea(
id="invoice",
readonly,
rows="5"
).form-control
```

Și să-l includem în index.pug

```
extends layout

block content
h1 Lightning App
include form.pug
include invoice.pug
```

## Modificarea App.sendBtn()

Acum modificăm App.sendBtn() pentru a afișa datele obținute:

```
App.sendBtn = async () => {
const name = $('#name').val();
const content = $('#content').val();
const response = await App.makeRequest({
api: "post",
post: { name, content },
});
if (!response) console.error('Eroare la obținerea datelor!');
if (response.success) {
$('#post-form').collapse('hide');
$('#invoice-form').collapse('show');
$('#invoice').val(response.data.request);
}
};
```

## Primirea plății
Trebuie să știm când primim plata, pentru aceasta vom folosi metoda `subscribeToInvoices()` din `lnservice`. Această metodă ne permite să executăm cod atunci când starea unei facturi a fost actualizată. Pentru a o utiliza, adăugăm aceste linii în `app.js`.

```javascript
// necesităm lnservice și tabelul nostru post
const lnservice = require('ln-service');
const post = require('./models/Post');

// autentificare cu lnd
const { lnd } = lnservice.authenticatedLndGrpc({
  cert: process.env.LND_CERT_BASE64,
  macaroon: process.env.LND_MACAROON_BASE64,
  socket: process.env.LND_GRPC_HOST,
});

// verificăm dacă factura a fost plătită de fiecare dată când o factură este actualizată
const subscribeInvoices = async () => {
  try {
    const sub = lnservice.subscribeToInvoices({lnd});
    sub.on('invoice_updated', async invoice => {
      if (!invoice.is_confirmed) return;

      // marcăm factura ca 'plătită'
      const paid = post.paid(invoice.id);
      if (paid) console.log('Factura plătită!');
    });

  } catch (e) {
    console.log(e);
    return e;
  }
};
// începem abonamentul la facturi
subscribeInvoices();
```

Creează o metodă HTTP GET în API-ul nostru pentru ca utilizatorul să verifice dacă un hash a fost plătit.

```javascript
router.get('/post/:hash', (req, res) => {
  const { hash } = req.params;
  const data = post.findByHash(hash);
  if (!!data) {
    return res.json({
      success: true,
      data,
    });
  } else {
    return res.json({
      success: false,
      data: null,
    });
  }
});
```

Acum, din `main.js`, creăm o funcție numită `App.waitPayment()` care interoghează API-ul dacă plata a fost efectuată.

```javascript
App.waitPayment = async (hash) => {
  const response = await App.makeRequest({
    api: `post/${hash}`,
  });
  if (response.success && response.data.paid) {
    console.log("Plată efectuată");
  }
};
```

Acum întâmpinăm o problemă, funcția `App.waitPayment()` este executată doar o dată, utilizatorul poate fi efectuat plata și noi nu am putut indica faptul că plata lor a fost primită. Pentru aceasta, folosim o funcție JavaScript numită `setInterval()` care ne permite să executăm o funcție la nesfârșit la intervalul de timp pe care l-am indicat.

Să modificăm funcțiile `App.waitPayment()` și `App.sendBtn()` incluzând `setInterval()` și `clearInterval()`

```javascript
App.waitPayment = async (hash) => {
  const response = await App.makeRequest({
    api: `post/${hash}`,
  });
  if (response.success && response.data.paid) {
    clearInterval(App.interval);
    App.interval = null;
    $("#invoice-form").collapse("hide");
    $("#preimage").text(response.data.preimage);
    $("#success").collapse("show");
  }
};

App.sendBtn = async () => {
  const name = $("#name").val();
  const content = $("#content").val();
  const response = await App.makeRequest({
    api: "post",
    post: { name, content },
  });
  if (!response) console.error("Eroare la obținerea datelor!");
  if (response.success) {
    $("#post-form").collapse("hide");
    $("#invoice-form").collapse("show");
    $("#invoice").val(response.data.request);
    App.interval = setInterval(App.waitPayment, 1000, response.data.hash);
  }
};
```
Și creăm o vedere pentru a indica faptul că plata a fost primită cu succes, creăm fișierul success.pug în views cu următorul conținut:
```pug
.collapse#success
  h2 Plată reușită
  div Dovadă de plată:
    #preimage
```

Îl includem în index.pug.

```pug
extends layout

block content
  h1 Aplicație Lightning
  include form.pug
  include invoice.pug
  include success.pug
```

Dacă după ce ai plătit factura poți vedea mesajul "Plată reușită" și dovada plății, felicitări!!! ai reușit, ai terminat prima ta LApp.