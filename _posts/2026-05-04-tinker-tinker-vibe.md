---
layout: post
title: Tinker, tinker, vibe!
image: "https://www.lassestorgaard.no/assets/images/tinkering.png"
category: Ai
author: Me
---

Kunstig intelligens gjør det helt absurd enkelt å tukle med teknologi.
Nå har jeg brukt flere KI verktøy siden den slags ble populært.

Litt pga. jobb, men mest pga. det er gøy. Jeg har brukt litt ChatGPT til å lage Vibe kodet hobby prosjekter her hjemme. Men syntes litt den og de andre har slitt med å treffe på å bli helt bra. Copilot hjulpet litt til i VSCode og Github. Kanskje mest med feil, men var aldri helt sånn at nå lager vi et prosjekt fra ende til annen.

Typisk syntes jeg ChatGPT og Copilot har slitt med hvor raskt ting endrer seg innen FOSS programvare. Rammeverk føltes som går en hovedversjon opp i halvåret og tydeligvis ikke noe som _Chat_ & _Copiloten_ klarer å henge med på. Hvilket jeg egentlig utemerket kan forstå fordi det kan ikke jeg heller. Det går rett å slett for hurtig. Og det er litt interessant hvordan en modell da løpende må oppdateres med nye data for å overkommer endringstakten.

Lovable.dev og Base44 var ganske kule, men løp så fort tørr for Credits og følte kanskje man kom litt vel langt unna selve koden for min del. Men er jo et kult LowCode-ish/Citizen development med fast teknologi plattform. Gjør kanskje det litt enklere for verktøyene.

## Old stuff?
Alle sa jeg skulle bruke Claude Code istedet. ALLE. Selv jurister på jobb sa det. Så det prøvde jeg her i siste uke. Og det var var INSANE.

Jeg prøvde å lage meg en treningslogg. Den foreslog en enkelt test med Mysql lite, men jeg endret retningen til produksjon på internett, med WAF, cloudflare, TLS og kun Passkey autentisering. Underveis i prosessen oppdaget jeg den hadde brukt pakker som var 3-4 versjoner gamle, hvilket var litt spesielt. Kanskje kunne det tilskrives treningsunderlaget til LLM'en? Den rettet det raskt opp etter jeg bad den om å lage en liste over utdatert programvare og da tilbød den selv å ordne op i sakene.

![Fitlog login](https://www.lassestorgaard.no/assets/images/fitlog.png "Fitlog login med Passkey")


## Finnne på nye ting?
Men siden den kanskje var "trent" på å lage treningslogg, kunne det være spennende å prøve noe helt nytt som ingen andre har funnet på før. Og her kommer min ProxSQL ide til sin rett. Jeg bad den rett å slett å om lage meg Proxy for SQL traffik som konverterer data mellom server og klient til HTTP-trafik og gjør en OIDC autentisering. Og OMG den catchet ideen lynrask i første forsøk!

Den foreslo å bruke Go og Keycloak, og satte igang. Rebuild av containere, feilfinding, konfig av Keycloak og 5-6 timer med fikling så hadde jeg en Proof of Concept på man faktisk kan få få en slik Proxy til å fungere. 

Jeg kunne kople min Mysql Workbench til min container, kontaineren trigget en Auth mot Keycloak, Keycloak ga tilbake en token og HTTP tunellen ble åpnet mot Server kontaineren - og You are logged in!.

Sekundet senere ble tunellen stengt igjen. Lurer på om det er noe rot med oppgradering til WebSocket, men ikke desto mindre så fungerte det. Neste steg er nok å få den stabil og få sett litt på hvor skalerbar den er ytelsesmessig på server kontaineren.

## I'm a n00b
Og det er litt greiene, jeg er ikke en utvikler jeg er en n00b. Men jeg digger å lære om teknologi og i min jobb så trenger jeg virkelig å forstå teknoglogi. Med Claude Code i hånda så er jeg i stand til å ta ganske avanserte FOSS applikasjoner og rammeverk ned til et "Tinker" nivå og for meg er det helt insane bra hvor jeg lærer utrolig mye! For meg så handler det om å få den sparringspartneren som ikke blir lei av mine dumme spørsmål.

_Og som tilfeldigvis kan lempe ut 16 kodefiler med Go og Docker._