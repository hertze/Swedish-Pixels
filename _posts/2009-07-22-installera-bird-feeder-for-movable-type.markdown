---
title: Installera Bird Feeder för Movable Type
layout: post
---

Jag uppskattar att hälften av Swedish Pixels läsare sällan besöker sajten, utan läser den i sin nyhetsläsare. [Bird Feeder][2], ett instick till Shaun Inmans [Mint][1], spårar syndikeringsflöden (RSS och ATOM) och ger mig möjlighet att hålla koll även på prenumeranter. Här beskriver jag *en* metod att få Bird Feeder att fungera med ett statiskt syndikeringsflöde publicerat genom Movable Type.[^2009-07-22-1]

Denna text är till en början skriven som en egen minnesanteckning, men sedan insåg jag att någon annan kanske skulle ha nytta av den. Det tog mig en hel kväll att få en fungerande lösning -- tid som jag gärna använt till annat.

1. Ladda ner Bird Feeder och ladda upp filerna till din server, enligt instruktionerna i den medföljande ReadMe-filen.
2. Förbered mallen för ditt flöde, genom att lägga till den PHP-kod som Inman beskriver i avsnitten "Preparing non-PHP feeds for Bird Feeder", punkt 2, samt "Adding Bird Feeder to your Feeds", punkt 1 och 2.
3. Expandera "Template Options", nedanför redigeringsfönstret i Movable Type, och ange att ATOM-filen skall sparas med filändelsen `.php`, i mitt fall `masterfeed.php`.
4. Min server kräver att PHP-filer sparas med *permissions 765*, för att kunna exekveras, annars skickar den ett 500-fel. Movable Type sparar filer med permissions *666* som förval, men detta kan man ändra genom att lägga till "`HTMLPerms 0777`" och "`HTMLUmask 0022`" på var sin rad i konfigurationsfilen `/cgi-bin/mt/mt-config.cgi`.
5. Omdirigera till sist prenumeranter till ditt nya flöde, i mitt fall från `masterfeed.xml` till `masterfeed.php`, genom att lägga till "`Redirect 307 /masterfeed.xml http://swedishpixels.com/masterfeed.php`" i din `.htaccess`-fil. "307" anger att omdirigeringen är tillfällig, vilket i mitt fall är mer korrekt.
Omdirigeringen i steg 5 gör förändringen osynlig för gamla och nya besökare och gör det lätt att avlägsna spårningen om man så önskar.

**Uppdatering:** Vidare testning har visat att omdirigeringen i punkt 5 inte är den smartaste lösningen. Om man gör på det sätt som beskrivs där kommer nya prenumeranter att spara den nya adressen `masterfeed.php` i sin nyhetsläsare, vilket innebär bekymmer den dag du vill ta bort spårningen. Bättre är att istället använda *mod_rewrite* i sin `.htaccess`-fil, i mitt fall följande rader:

	RewriteEngine on

	RewriteRule ^masterfeed.xml$ http://swedishpixels.com/masterfeed.php [R=307,NC,L]

Denna omdirigering är helt osynlig för besökaren. Nya prenumeranter kommer att spara adressen `masterfeed.xml`, vilket var den ursprungliga avsikten.

[1]: http://haveamint.com
[2]: http://www.haveamint.com/peppermill/pepper/11/bird_feeder/

[^2009-07-22-1]: Jag låter Movable Type publicera hela min sajt, inklusive ATOM-flödet, som statiska filer. Om jag hade velat ha en dynamisk sajt finns det andra CMS att föredra.
