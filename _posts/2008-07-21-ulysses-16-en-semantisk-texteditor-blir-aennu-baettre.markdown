--- 
title:      Ulysses 1.6 — en semantisk texteditor blir ännu bättre
created_at: 2008-07-21 11:57:06.791401 +01:00
keywords:   ulysses, text editor
filter:     markdown
description: Joakim Hertze skriver på webben
layout:     post
---
doc_prefix: c2008-07-21

Den 1 juli släppte _Blue-Tec_ [Ulysses 1.6][1], efter ett par månader i sluten beta. Det är inga revolutionerande förändringar man gjort av sin kritikerrosade texteditor, men några saker är värda att notera:

- **Förbättrad utforskare.** Man har lagt till stöd för grupper, som hjälper dig att organisera samlingar och filter. Man kan nu fokusera en grupp, liknande den "hoisting" man kan se i outliners, varvid övriga grupper döljs.
- **Förbättrad förhandsgranskning.** Med ett musklick utvidgas fönstret för förhandsvisning, med ett klick till återgår det till vanlig storlek.
- **Förbättrad sök & ersätt**, där man nu kan söka efter markeringar och taggar.
- **Bättre stöd för teman.**
- **Fullskärmsläge**, ej att förväxla med konsolläge.
- **Förbättrad LaTeX-export.**

<img src="http://swedishpixels.com/bilder/31.jpg" style="float:right; margin: 0 0 4px 8px;" alt="Ulysses" /> 

Jag är ett stort fan av Ulysses och har varit så ända sedan jag upptäckte programmet för två år sedan. Med version 1.6 har det blivit ännu skarpare, men det finns en del bekymmer kvar att ta itu med. 

Även om utforskaren _har_ förbättrats en hel del är det fortfarande inte helt intuitivt att strukturera större projekt. Man har medvetet valt att förkasta den traditionella mapp-metaforen till fördel för filter och samlingar (ett modernt metadata perspektiv), vilket jag upplever som ett krystat sätt att uppfinna hjulet på nytt. Ulysses ligger efter sina konkurenter[^2] när det gäller organisatoriska verktyg. Framför allt efterlyser jag en _outline-vy_, något man verkar överväga för Ulysses 2.0.

Det finns inte heller ett inbyggt system för versionskontroll. Det är inte hela världen, då jag alltmer ser fördelar med att sköta detta utanför _utanför_ texteditorn. Ulysses datamodell lämpar sig emellertid inte för versionskontroll med programvara som [SubVersion][3]. En Ulyssesfil är egentligen ett paket, det vill säga en mapp. I detta representeras varje dokument i ditt projekt som en numrerad undermapp, innehållande fem filer[^1] och en ytterligare mapp för dina dokumentspecifika anteckningar. Detta gör strukturen helt oöverskådlig när projektet växer och det är snudd på omöjligt att hålla reda på i vilken numrerad mapp som ett visst dokument ligger sparat. Som grädde på moset sparar Ulysses även öppna dokument (de som visas som flikar) som numrerade mappar -- denna gång med prefixet _o_. Dessa skapas och tas bort för varje gång du öppnar ett nytt dokument i Ulysses, vilket är en rejäl nagel i ögat för SubVersion. Ett bra grafiskt gränssnitt, som [Versions][2], underlättar dock en hel del. Det går, men hade kunnat vara betydligt enklare.

Är inte detta system aningen komplicerat för en text editor ämnad för ren text? Jag hade gärna sett att man förenklat datamodellen en smula för att förenkla versionskontrollen. Varför inte försöka klara sig med rena textfiler så långt som möjligt? [TextMate][4] visar att mycket är möjligt. Ulysses tagg-system hade förmodligen gått att bygga med något som liknar _regular expressions_, markeringarna hade jag klarat mig utan.

Idag kämpar Blue-Tec i motvind i en marknad som plötsligt flödar över av program riktade mot kreativa skribenter. I en tid då användare blir alltmer bortskämda av transparens, ständiga bloggposter, tweets och punktuppdateringar från utvecklare provocerar man med att utveckla långsamt och under tystnad. Trots brister i versionskontroll och projektplanering är Ulysses fortfarande den bästa editorn för kreativa skribenter. Det krävs emellertid att man acceptera det grundläggande antagandet att ren text är att föredra framför RTF -- något majoriteten förmodligen inte håller med om. Det är lite som religion -- det finns inget rätt och fel här.

[^1]: Två textfiler, en RTF-fil, ett textarkiv och en .plist fil.

[^2]: Framför allt _Keith Blounts_ [Scrivener](http://www.literatureandlatte.com/scrivener.html).

[1]: http://blue-tec.com/ulysses
[2]: http://versionsapp.com
[4]: http://macromates.com
[3]: http://subversion.tigris.org/

