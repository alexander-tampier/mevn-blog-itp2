# MEVN Blog-feed für IT Projektarbeit 2 (ITPS)

Die Projektarbeit für `ITPS2 BIF-DUAL` wurde mit dem klassischen `MEVN-STACK (MongoDb, Express, VueJS, NodeJS)` realisiert. Als Datenbank steht eine `MongoDb` auf der Platform [mLab](https://mlab.com/ "MongoDB Hosting") zur Verfügung. Zuerst wurde lokal mit einer Mongo-Datanbank am `https://localhost:27017` entwickelt und mit Testdaten gearbeitet. Mit dem JavaScript-Framework `Express.js` erfolgt das Basisrouting im Backend. `Vue.js` wird im Frontend als Framework für das Router-Linking und das Rendering der angefragten Daten aus dem Backend verwendet.

## Vue.js

Vue.js ist ein clientseitiges JavaScript-Webframework zum Erstellen von Single-Page-Webanwendungen nach dem MVVM-Muster, es kann allerdings auch in Multipage Webseiten für einzelne Abschnitte verwendet werden. Ab Version 2.0 unterstützt es auch serverseitiges Rendern. Auf serverseitiges Rendern mit `Nuxt.js` wurde allerdings verzichtet. Das Rendering erfolgt lediglich direkt auf der Clientseite. 

## MongoDB (mLab)

mLab ist ein voll funktionaler Datenbank-Service der eine `MongoDB` hostet und läuft in der Cloud mit folgenden Anbietern

* Amazon
* Google
* Microsoft Azure

mLab hat Verbingungen zu diesen Platform-as-a-service Providern.

## Express.js

Basisrouting
Per *Routing* wird bestimmt, wie eine Antwort auf eine Clientanforderung an einem bestimmten Endpunkt antwortet. Dies ist eine URI (oder ein Pfad) und eine bestimmte HTTP-Anforderungsmethode (GET, POST usw.).

Jede Weiterleitung (Route) kann eine oder mehrere Handlerfunktionen haben, die ausgeführt werden, wenn die Weiterleitung abgeglichen wird.

Weiterleitungsdefinitionen haben die folgende Struktur:

```javascript
app.METHOD(PATH, HANDLER)
```

Bedeutung:

* *app* ist eine Instanz von express.
* *METHOD* ist eine HTTP-Anforderungsmethode.
* *PATH* ist ein Pfad auf dem Server.
* *HANDLER* ist die Funktion, die ausgeführt wird, wenn die Weiterleitung abgeglichen wird.

## Filestruktur am Server

## Überblick der Dateien

## Dateien Kurzbeschreibung und Funktionalität

## Beschreibung des Source als Klassendiagramm

## Beschreibung der Datenbank

## Deployment

## Verwendung der Technologien und third-party tools

* netlify
* cloudinary
* materialize.css
* vuejs
* nodejs
* github
* mLab 
* heroku

## Live Demo

https://loving-shockley-d34b21.netlify.com/
