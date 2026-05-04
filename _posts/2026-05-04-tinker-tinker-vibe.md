---
layout: post
title: Tinker, tinker, vibe!
image: "https://www.lassestorgaard.no/assets/images/tinkering.png"
category: Ai
author: Me
---

Kunstig intelligens gjør det helt absurd enkelt å tukle eller mekke med teknologi.
Nå har jeg brukt flere KI verktøy siden det ble populært.
Litt pga. jobb, men mest pga. det er gøy. Eller det man kan gjøre med de er gøy da. Åssen ser det ut om jeg bare lager en veldig veldig lang linje?

...*


Jeg har brukt flere KI verktøy nå siden det fikk sin vår. Det har vært gøy, rett
og slett. Men ikke så mye mer enn gøy. For meg startet jeg med Midjourney. Og det
var jo veldig gøy, men ikke riktig så nyttig for meg. Copilot fikk jeg litt tvunget
ned i halsen av Microsoft, først på jobb med insane mengde hype, også hjemme da 
måket det inn i samtlige produkter og abonnementer. ChatGPT var frivillig og litt
sånn av å på. Prøvde å kode litt med ChatGPT, men stødte hurtig på problemer "den"
gjorde feil og som rett å slett var for vanskelig å løse. Det var mye rundt FOSS
programvare som den åbenbart ikke klarte å henge med på. Hvilket jeg egentlig 100%
kan gjenkjende. 

Lovable.dev og Base44 var ganske kule, men løp så fort tørr for Credits og følte
kanskje man kom litt vel langt unna selve koden for min del.

## Old stuff?
Alle sa jeg skulle bruke Claude Code istedet. ALLE. Selv jurister på jobb sa det. 
Så det prøvde jeg her i siste uke. Og det var var INSANE. 

Jeg prøvde å lage meg en treningslogg. Den foreslog en enkelt test med Mysql lite,
men jeg endret retningen til produksjon på internett, med WAF, cloudflare, TLS og
kun Passkey autentisering. Underveis i prosessen oppdaget jeg den hadde brukt pakker
som var 3-4 hoved releaser gamle, hvilket var litt spesielt. Kanskje kunne det 
tilskrives treningsunderlaget til LLM'en? Etter jeg bad den om å lage en liste over
utdatert programvare tilbød den selv å ordne op i sakene og gjorde det veldig bra.

![Fitlog login](https://www.lassestorgaard.no/assets/images/fitlog.png "Fitlog login med Passkey")


## Finnne på nye ting?
Men siden den kanskje var "trent" på å lage treningslogg, kunne det være spennende
å prøve noe helt nytt som nok ikke så mange har funnet på før. Og her kommer min 
ProxSQL ide til sin rett. Jeg bad den rett å slett å om lage meg Proxy for SQL 
traffik som konverterer data mellom nodene til HTTP og gjør en OIDC autentisering.
Og OMG den catchet ideen lynrask i første forsøk! I nettleseren forslo den NodeJS 
som verktøy, i VSCode gikk den for Go.
Men en masse spørre frem og tilbake. Rebuild av containere, feilfinding, konfig 
av Keycloak og 5-6 timer mekking hadde: Da hadde jeg en POC som virket!
Jeg kunne kople min Mysql Workbench til min container, kontaineren trigget en Auth
mot Keycloak, Keycloak ga tilbake en token og HTTP tunellen ble åpnet mot Server
kontaineren - og You are logged in!.

Sekundet senere ble tunellen stengt igjen. Lurer på om det er noe rot med oppgradering
til WebSocket, men ikke desto mindre så fungerte det.

## I'm a n00b
Og det er litt greiene, jeg er ikke en utvikler jeg er en n00b. Men jeg digger å lære
om teknologi og i min jobb så trenger jeg virkelig å forstå teknoglogi. Med Claude Code
i hånda så er jeg i stand til å ta ganske avanserte FOSS applikasjoner og rammeverk 
ned til et "Tinker" nivå og for meg er det helt insane bra hvor jeg lærer utrolig mye!
For meg så handler det om å få den sparringspartneren som ikke blir lei av mine dumme
spørsmål.

_Og som tilfeldigvis kan lempe ut 16 kodefiler med Go og Docker._