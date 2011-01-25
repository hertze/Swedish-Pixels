--- 
title:       Synkronisera med Dropbox och symlinks
created_at:  2009-01-03 09:50:11.791401 +01:00
keywords:    dropbox, symlinks, synkronisera
description: Alla som regelbundet använder mer än en dator lär ställas inför problemet att hålla dem i synk [...] Till sist tror mig  ha funnit ett gratis och fungerande alternativ; en kombination av Unix-magi och Dropbox.
layout:      post
---
doc_prefix: c2009-01-03

Alla som regelbundet använder mer än en dator lär ställas inför problemet att hålla dem i synk. Apple har ju sin [MobleMe] [4], som på pappret löser en hel del av dessa bekymmer, men arga röster på nätet gör gällande att tjänsten fungerar långt ifrån optimalt. Dessutom är den snordyr.

Jag har provat en del alternativ, senast [ChronoSync] [5], men ingenting har fungerat smidigt. Allt som kräver att jag måste _göra något_ varje dag -- om än något så trivialt som att se till att båda datorerna lämnas påslagna på natten -- har varit dömt att misslyckas.

Till sist tror mig  ha funnit ett gratis och fungerande alternativ; en kombination av *Unix-magi* och [*Dropbox*] [1].

Jag laddade ner och installerade Dropbox på mina båda datorer. Jag skrev tills vidare upp mig för gratiskontot med 2 Gb lagringsutrymme.

Den information jag behöver ha synkroniserad är min adressbok, mina iCal-kalendrar, min Yojimbo-databas[^1] och min Things-databas[^2]. Dessutom har jag tre mappar som jag vill ha tillgängliga på båda datorer.[^3]

Things var enkelt att lösa. Jag flyttade helt enkelt mappen `~/Library/Application Support/Things` till Dropbox-mappen. När jag sedan startade Things höll jag ner _Alt_-tangenten och valde databasen i Dropbox-mappen i den dialogruta som visades.

För mina tre mappar var det inte svårare än att flytta över dem till Dropbox-mappen och skapa alias på de ställen där de tidigare legat.

När det gäller Yojimbo, Adressboken och iCal behövde jag vara lite mer kreativ. Med hjälp av Unix _symboliska länkar_ (symlinks) kunde jag lura Addressbook.app, iCal.app och Yojimbo.app att deras filer låg kvar där de brukade, trots att jag flyttat dem alla till min Dropbox-mapp.

Principen är enkel och jag använder här Yojimbo som modell. Jag avslutade programmet och flyttade mappen `~Library/Application Support/Yojimbo` till min Dropbox-mapp. Sedan öppnade jag Terminal.app och körde följande kommando:

	ln -s ~/Dropbox/Yojimbo ~/Library/Application\ Support/
	
På min andra dator kastade jag helt enkelt mappen `~Library/Application Support/Yojimbo` och körde därefter samma kommando i terminalen. Voilá! Mitt Yojimbobibliotek synkroniseras nu mellan mina båda datorer.

Jag gjorde på motsvarande sätt med adressboken och iCal. Hittills har allt fungerat förträffligt.



[1]: http://www.getdropbox.com/
[2]: http://www.barebonessoftware.com/products/yojimbo/
[3]: http://culturedcode.com/things
[4]: http://me.com
[5]: http://www.econtechnologies.com/site/Pages/ChronoSync/chrono_overview.html

[^1]: Jag använder [Yoijmbo] [2], från Bare Bones Software, som digitalt _catch-all_ arkiv. Yojimbo synkar även via MobileMe, fast det fungerar tydligen inte helt bekymmersfritt.

[^2]: Jag använder [Things] [3], från Cultured Code, som GTD-program. Man säger sig arbeta på en inbyggd funktion för dator--till--dator synkronisering, men ännu så länge får man lösa problemet efter eget huvud.

[^3]: En mapp med namnet "arkiv", en med namnet "pågående" och en med namnet "utkorg". Jag har en "inkorg" också, men den har jag valt att inte göra gemensam.