--- 
title:       Forma dina webbadresser med .htaccess och regular expressions
created_at:  2009-03-16 10:38:00.791401 +01:00
keywords:    htaccess, unix, regex, regular expressions, redirect, omdirigering, URI, filändelser, file extensions
description: Eftersom den här sajten består av statiska sidor på en Apache-server är en .htaccess-fil den enda sätt jag känner till att lösa problemet. Genom otaliga Google-sökningar och en hel del experimenterande kom jag fram till följande innehåll i min egen .htaccess-fil.
layout:      post
---
doc_prefix: c2009-03-16

När jag för en tid sedan bytte publiceringssystem fick jag plötsligt själv ansvar för hur adresserna (URI[^2]) till sidorna skulle se ut. Jag ville att de alla skulle ha formen `http://swedishpixels.com/år/månad/titel`, vilket jag själv tycker ger såväl tillräcklig som nödvändig information för att vara användbart.

Då mina sidor egentligen är XHTML-filer var jag tvungen att trolla bort filändelsen `.html`.[^1] Dessutom var jag tvungen att se till att det bara fanns *en* adress till varje sida. Google tycker nämligen illa om när flera adresser pekar mot samma innehåll, vilket skulle kunna resultera i att man utesluts ur deras index.

Eftersom den här sajten består av statiska sidor på en Apache-server är en `.htaccess`-fil den enda sätt jag känner till att lösa problemet. För mig är dessa filer, placerade i roten på ditt webbhotell, en obehaglig blandning av Unix och [regular expressions][2], som jag aldrig riktigt förstått. Genom otaliga Google-sökningar och en hel del experimenterande kom jag fram till följande innehåll i min egen `.htaccess`-fil:


     1  #Options +FollowSymLinks
     2  #Options -Indexes
     3        
     4  RewriteEngine on
     5       
     6  RewriteCond %{REQUEST_FILENAME} !-d
     7  RewriteRule ^(.+)/$ /$1 [R=301,L]
     8        
     9  RewriteCond %{THE_REQUEST} (.*)(\.)html 
    10  RewriteRule ^(.*)\.html$ /$1 [R=301,L]
    11       
    12  RewriteCond %{REQUEST_FILENAME} !-d
    13  RewriteCond %{REQUEST_FILENAME}\.html -f
    14  RewriteRule ^(.*[^/])/?$ $1.html [L]

Vi bryter ner det hela och börjar från slutet:

	12  RewriteCond %{REQUEST_FILENAME} !-d
	13  RewriteCond %{REQUEST_FILENAME}\.html -f
	14  RewriteRule ^(.*[^/])/?$ $1.html [L]

Denna kodsnutt skriver *internt* om alla adresser av formen `http://foo/bar` och `http://foo/bar/` och omdirigerar dem till `http://foo/bar.html`. Detta blir aldrig synligt för besökaren, utan det ser ut som om sidorna saknar filändelser. 

Om jag hade nöjt mig med denna kod skulle `http://foo/bar`, `http://foo/bar/` och `http://foo/bar.html` alla ha visat samma sida för besökaren. Google och andra söktjänster hade förmodligen indexerat vart och ett av de tre alternativen som en distinkt adress. Möjligen hade detta inte varit ett bekymmer om jag hade total kontroll över hur *inkommande* länkar ser ut, men sådan är förstås inte verkligheten. Istället behövs här mer Unix-magi:

 	9  RewriteCond %{THE_REQUEST} (.*)(\.)html 
	10  RewriteRule ^(.*)\.html$ /$1 [R=301,L]

Denna snutt skriver *externt* om adresser av formen `http://foo/bar.html` till `http://foo/bar`, vilket är synligt för besökaren. Vid omdirigeringen skickas  HTTP-statuskoden "301", vilket betyder "permanent flyttad". Google, och andra indexeringstjänster, tolkar detta som att det är `http://foo/bar` som gäller och indexerar bara den adressen.

	6  RewriteCond %{REQUEST_FILENAME} !-d
	7  RewriteRule ^(.+)/$ /$1 [R=301,L]
	
Denna första snutt skriver *externt* om adresser av formen `http://foo/bar/` till `http://foo/bar`. Även här skickas statuskoden "301" och därmed är säcken hopknuten.

Jag är väl medveten om att det förmodligen finns lösningar som både är mer korrekta och mer eleganta. Den här fungerar emellertid och jag känner ett visst ansvar att föra upptäckten vidare.

[^1]: Visserligen kanske inte en sådan filändelse stör nämnvärt, men de tillför ingen användbar information för besökaren. *World Wide Web Consortium* [rekommenderar][1] dessutom att man skippar filändelser för öka möjligheterna för bevarade adresser vid framtida teknikskiften.

[^2]: Universal Resource Identifier

[1]: http://www.w3.org/Provider/Style/URI
[2]: http://www.regular-expressions.info/