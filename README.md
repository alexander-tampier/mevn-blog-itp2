# MEVN Blog-feed für IT Projektarbeit 2 (ITPS)

Die Projektarbeit für `ITPS2 BIF-DUAL` wurde mit dem klassischen `MEVN-STACK (MongoDb, Express, VueJS, NodeJS)` realisiert. Als Datenbank steht eine `MongoDb` auf der Platform [mLab](https://mlab.com/ "MongoDB Hosting") zur Verfügung. Zuerst wurde lokal mit einer Mongo-Datanbank am `https://localhost:27017` entwickelt und mit Testdaten gearbeitet. Mit dem JavaScript-Framework `Express.js` erfolgt das Basisrouting im Backend. `Vue.js` wird im Frontend als Framework für das Router-Linking und das Rendering der angefragten Daten aus dem Backend verwendet. `Node.js` wird im Backend verwendet um die Daten aus der Datenbank zur Verfügung zu stellen. Das Backend unterstützt klassische `CRUD (Create, Read, Update, Delete)` Funktionalitäten. 

![MEVN-Architecture](https://raw.githubusercontent.com/alexander-tampier/mevn-blog-itp2/master/public/hn-architecture.png "MEVN-Architecture")

## Technologiestack

### MongoDB (mLab)

mLab ist ein voll funktionaler Datenbank-Service der eine `MongoDB` hostet und läuft in der Cloud mit folgenden Anbietern

* Amazon
* Google
* Microsoft Azure

mLab hat Verbingungen zu diesen Platform-as-a-service Providern.

### Express.js

Basisrouting
Per *Routing* wird bestimmt, wie eine Antwort auf eine Clientanforderung an einem bestimmten Endpunkt antwortet. Dies ist eine URI (oder ein Pfad) und eine bestimmte HTTP-Anforderungsmethode (GET, POST usw.).

Jede Weiterleitung (Route) kann eine oder mehrere Handlerfunktionen haben, die ausgeführt werden, wenn die Weiterleitung abgeglichen wird.

Weiterleitungsdefinitionen haben die folgende Struktur:

```javascript
app.METHOD(PATH, HANDLER)
```

Bedeutung:

* **app** ist eine Instanz von express.
* **METHOD** ist eine HTTP-Anforderungsmethode.
* **PATH** ist ein Pfad auf dem Server.
* **HANDLER** ist die Funktion, die ausgeführt wird, wenn die Weiterleitung abgeglichen wird.

### Vue.js

Vue.js ist ein clientseitiges JavaScript-Webframework zum Erstellen von Single-Page-Webanwendungen nach dem MVVM-Muster, es kann allerdings auch in Multipage Webseiten für einzelne Abschnitte verwendet werden. Ab Version 2.0 unterstützt es auch serverseitiges Rendern. Auf serverseitiges Rendern mit `Nuxt.js` wurde allerdings verzichtet. Das Rendering erfolgt lediglich direkt auf der Clientseite.

### Materialize.css (Material Design)

Material Design ist eine Design-Sprache die 2014 von Google entwickelt wurde. Es beinhalter Grid-basierende Layouts, responsive Animations und transitions sowie paddings und tiefere Licht und Schatteneffekte.

### Node.js

Um die Daten aus dem Backend zu manipulieren werden klassische `CRUD` Funktionen zur Verfügung gestellt.

#### Express Router and Routes

Die folgende Tabelle bietet eine Übersicht über alle Routen mit jeweiliger Funktionalität und dem zugehörigen `HTTP Verb` um darauf zuzugreifen.

| Route               | HTTP Verb | Description                  |
|---------------------|-----------|------------------------------|
| /api/posts          | `GET`       | Get all the posts.           |
| /api/posts          | `POST`      | Create a post.               |
| /api/posts/:post_id | `GET`       | Get a single post.           |
| /api/posts/:post_id | `PUT`       | Update a post with new info. |
| /api/posts/:post_id | `DELETE`    | Delete a post.               |

### Cloudinary

Cloudinary ist eine Software-as-a-Service Technologie-Firma. Es wird eine cloud-based Lösung für Videos und Bilder angeboten. Dadurch sind Benutzer im Stande Dateien für verschiedene Websites und Applikationen hochzuladen, zu verwalten, zu manipulieren und auszuliefern. Cloudinary wird von Entwicklern für Web und mobile Applikationen verwendet.

## Heroku

Heroku ist eine Platform-as-a-Service *(PaaS)* Applikation die unterschiedliche Programmiersprachen unterstützt. Hier können verschiedene Container gehostet werden. Heroku war eine der ersten Cloud-Plattformen, die anfänglich lediglich die Ruby-Programmiersprache unterstützte. Allerdings können nun viele andere *Middleware/Backend* Sprachen auf einem Heroku-Container ausgeführt werden wie beispielsweise Java, Node.js, Scala, Clojure, Python, PHP und Go. Entwickler können auf Heroku ihre Applikationen builden, laufen lassen und diese skalieren.

## Netlify

### Continious Deployment

Netlify ist ein Tool mit einem intuitivem Online-Interface um Webseiten zu deployn in nur wenigen Sekunden. Es ist zudem kostenlost für eine unlimitierte Anzahl an Projekten für eine Person. Dadurch ist es das Ideal für persönliche oder kleine Projekte sowie für Projekte mit einem *educational purpose* wie dieses hier.  

#### Continuous Deployment

Für alle Projekte die größer werden als lediglich eine Landing-Page sollte ein static site Generator oder ein Frontend build tool wie beispielsweise `grunt` oder `gulp` verwendet werden. In diesem Projekt wird allerding `webpack` zum Bundlen der Files verwendet. 

Über Netlify kann das jeweilige `Github repository` mit der Seite verbunden werden. Jedes mal wenn also auf `GitHub` gepusht wird, lässt `Netlify` einen build durchlaufen der automatisch auf das `Content-Delivery-Network` deployt.

## Filestruktur am Server

```
|-- mevn-blog-itp2
    |-- .env
    |-- .eslintrc.js
    |-- .gitignore
    |-- .tern-project
    |-- LICENSE
    |-- README.md
    |-- app.js
    |-- package-lock.json
    |-- package.json
    |-- bin
    |   |-- post.json
    |-- config
    |   |-- logger.js
    |-- model
    |   |-- post.js
    |-- public
    |   |-- images
    |       |-- card-picture-four.jpg
    |       |-- card-picture-one.jpg
    |       |-- card-picture-three.jpg
    |       |-- card-picture-two.jpg
    |       |-- pexels-photo-1020315.jpg
    |       |-- pexels-photo-236093.jpg
    |       |-- pexels-photo-590493.jpg
    |       |-- pexels-photo-908284.jpg
    |       |-- pexels-photo-977296.jpg
    |-- routes
        |-- router.js
```

## Überblick der Dateien am Server

* `.env` - Wird benutzt um die properties zu setzen für `MONGODB_USERNAME` und `MONGODB_PASSWORD` um eine Verbindung zur mLab mongoDB herzustellen. Alternativ kann `MONGODB_URI` auf `localhost:27017/my-collection` gesetzt werden um den Connector mit einer lokalen MongoDB zu verbinden.
* `.eslintrc.js` - ESLint ist ein statisches Code-Analyse-Tool dass von den meisten Entwicklern verwendet wird um den JavaScript source code auf kompatible Regeln zu überprüfen.
* `.gitignore` - Wird verwendet um generierte Dateien nicht am Github-Repository zu hosten.
* `tern-project` - Tern ist eine stand-alone Code-Analyse Umgebung für JavaScript. Es wird verwendet um intelligentes JavaScript editing zu aktiveren in einer belibiegen Entwicklungsumgebung.
* `app.js` - In der app.js Datei werden alle wichtigen Abhängigkeiten deklariert und der Server wird auf einem bestimmten Port gestartet.
* `package.json` - Deklariert alle Dependencies im Projekt
* `bin/` - Der Entwurf einer Response eines einzelnen Blog-Feed
* `config/` - Eigens konfigurierte logger
* `model/` - Schema für die Datenbank wird erstellt
* `routes/` - Definiert alle Endpoints


## Filestruktur am Client

```
|-- mevn-blog-itp2
    |-- .babelrc
    |-- .editorconfig
    |-- .eslintignore
    |-- .eslintrc.js
    |-- .gitignore
    |-- .postcssrc.js
    |-- LICENSE
    |-- README.md
    |-- index.html
    |-- package-lock.json
    |-- package.json
    |-- build
    |   |-- build.js
    |   |-- check-versions.js
    |   |-- logo.png
    |   |-- utils.js
    |   |-- vue-loader.conf.js
    |   |-- webpack.base.conf.js
    |   |-- webpack.dev.conf.js
    |   |-- webpack.prod.conf.js
    |   |-- webpack.test.conf.js
    |-- config
    |   |-- dev.env.js
    |   |-- index.js
    |   |-- prod.env.js
    |   |-- test.env.js
    |-- docs
    |   |-- index.html
    |   |-- static
    |       |-- css
    |       |   |-- app.3d8326f6cc7fba01780eef73bb14ea23.css
    |       |   |-- app.3d8326f6cc7fba01780eef73bb14ea23.css.map
    |       |   |-- app.65366bafd1f8ee7f998032855276d8c3.css
    |       |   |-- app.65366bafd1f8ee7f998032855276d8c3.css.map
    |       |-- js
    |           |-- app.b094bac0ec362eec0a75.js
    |           |-- app.b094bac0ec362eec0a75.js.map
    |           |-- app.fcdf1f909dfd81e65cfc.js
    |           |-- app.fcdf1f909dfd81e65cfc.js.map
    |           |-- manifest.223214398829f137c148.js
    |           |-- manifest.223214398829f137c148.js.map
    |           |-- manifest.2ae2e69a05c33dfc65f8.js
    |           |-- manifest.2ae2e69a05c33dfc65f8.js.map
    |           |-- vendor.006781ede95bb2071b59.js
    |           |-- vendor.006781ede95bb2071b59.js.map
    |-- helper
    |   |-- truncate.js
    |-- src
    |   |-- App.vue
    |   |-- main.js
    |   |-- assets
    |   |   |-- logo.png
    |   |-- components
    |   |   |-- BlogDashBoard.vue
    |   |   |-- BlogPost.vue
    |   |   |-- Navbar.vue
    |   |-- router
    |   |   |-- index.js
    |   |-- services
    |       |-- Api.js
    |       |-- PostService.js
    |-- static
    |   |-- .gitkeep
    |   |-- css
    |   |   |-- app.65366bafd1f8ee7f998032855276d8c3.css
    |   |   |-- app.65366bafd1f8ee7f998032855276d8c3.css.map
    |   |-- js
    |       |-- app.fcdf1f909dfd81e65cfc.js
    |       |-- app.fcdf1f909dfd81e65cfc.js.map
    |       |-- manifest.223214398829f137c148.js
    |       |-- manifest.223214398829f137c148.js.map
    |       |-- vendor.006781ede95bb2071b59.js
    |       |-- vendor.006781ede95bb2071b59.js.map
    |-- test
        |-- e2e
        |   |-- nightwatch.conf.js
        |   |-- runner.js
        |   |-- custom-assertions
        |   |   |-- elementCount.js
        |   |-- specs
        |       |-- test.js
        |-- unit
            |-- .eslintrc
            |-- index.js
            |-- karma.conf.js
            |-- specs
                |-- HelloWorld.spec.js
```

## Überblick der Dateien am Client

* `babelrc` - Kompatibilität für ältere Browser
* `build/` - Webpack build folder um das Projekt zu bundlen
* `config/` - Alle config files für die einzelnen Umgebungen wie `dev`, `test` und `prod`
* `docs/` - Static Assets für das Deployment am Netlify-CDN
* `helper` - Interne JavaScript-Funktionen um den Title und den Content eines Posts zu truncaten.
* `src/` - Der eigentliche Source-Code des Projekts für den Blog-feed
  * `components/` - Widerverwendbare Komponenten wie z.B ein einzelner Blog-Post oder die Navigationsbar für das frontend
  * `router/` - Internes Router-Linking für die einzelnen Routes der Webapplikation
  * `services/` - `REST` Calls zum `Node.js` Backend um alle BlogPosts zu erhalten oder lediglich einen einzelnen

## Live Demo

https://loving-shockley-d34b21.netlify.com/
