--- 
title:       Om Webby och strävan efter enkelhet
created_at:  2009-03-09 19:17:17.791401 +01:00
keywords:    webby, CMS, content management system, statiska filer, Textpattern, blogg
description: Jag använder nu inte längre TextPattern, utan alla sidor skapas som statiska XHTML-filer på min hårddisk. Dessa sidor synkroniseras sedan med min webbserver. Jag skriver rena textdokument uppmärkta med Markdownoch låter sedan Webby sätta samman de sidor du ser nu.
layout:      post
---
doc_prefix: c2009-03-09

För en tid sedan vädrade jag [mina funderingar][3] kring framtiden för min blogg. Jag var innerligt trött på mitt publiceringssystem och det underhåll som följde med det. Jag hade egentligen tänkt överlägga länge och väl, men plötsligt hade jag byggt om alltihop. Det fanns en viss tillfredsställelse i det.

<img src="/bilder/blogfolder.jpg" style="float: right; margin: 0 0 4px 8px;" />

Jag använder nu inte längre [TextPattern][2], utan alla sidor skapas som statiska XHTML-filer på min hårddisk. Dessa sidor synkroniseras sedan med min webbserver. Jag skriver rena textdokument uppmärkta med [Markdown][7] och låter sedan [Webby][1] sätta samman de sidor du ser nu. Den stora fördelen med detta är att jag alltid har en lokal säkerhetskopia, som är underkastad revisionskontroll[^2] och som är sökbar via [Spotlight][5]. Jag kände mig egentligen aldrig bekväm med att hantera en  MySQL-databas på en server i USA. 

Sajtens uppbyggnad är nu i mångt och mycket ett experiment. Jag har haft som mål att göra strukturen så enkel som möjligt och har därför skurit bort allt som inte är nödvändigt. Tanken är att det skall bli så lite underhåll som möjligt för mig. Jag låter nu Google sköta sökfunktionen och har medvetet valt att inte erbjuda en arkivsida, där alla texter listas i datumordning. Jag frågade mig hur ofta jag själv egentligen kollade på sådana förteckningar och insåg att det var ovanligt. För att öka chanserna för att Google skall indexera *alla* sidor har jag istället försett sajten med en webbplatskarta.[^1]

Jag har skippat artikelkategorier och taggar, då de för mig blivit ännu ett element utan tydlig nytta. Det ständiga klassificerandet hade blivit till ett hinder för mig -- en barriär som jag skulle över varje gång jag publicerade en text.

Nackdelen med ett statiskt system är att det är svårare att erbjuda kommentarer. Det går visserligen med externa javascript-system, som [Disqus][6], men jag har valt att avvakta. När jag tittade igenom mina gamla texter märkte jag att mycket var skrivet i syfte att provocera fram läsarreaktioner. Ett inlägg kändes aldrig riktigt lyckat förrän det hängde ett antal kommentarer under, som smultron på ett grässtrå. Det blev pladdrigt och ofta kändes det som jag gick runt med håven. Detta innebär *inte* att jag inte bryr mig om vad du som läsare tycker. Tvärt om. Jag tar gärna emot synpunkter via epost. Adressen finns i sidfoten.

Slutligen har jag flyttat allt innehåll hit till *swedishpixels.com*. Det var inget beslut jag tog lätt på, men nu känns det rätt. Jag hade länge känt ett obehag inför att skriva mina texter under domännamnet *hertze.com*. På något sätt kändes det för intimt kopplat till mig som person. Nu känns det som jag skriver *produkten* Swedish Pixels, istället för att försöka bygga ett varumärke kring mitt eget namn.


[1]: http://webby.rubyforge.org/
[2]: http://textpattern.com
[3]: http://www.swedishpixels.com/2009/02/aer-det-dags-att-avliva-bloggen
[4]: http://getdropbox.com
[5]: http://en.wikipedia.org/wiki/Spotlight_(software)
[6]: http://disqus.com
[7]: http://daringfireball.net/projects/markdown/

[^1]: Ett XML-dokument, med adresser till alla sidor. Google rekommenderar själva att man använder sig av en sådan i de fall alla sidor inte går att nå via länkar från andra sidor.

[^2]: Jag använder [Dropbox][4], för dess enkelhet. Det hade förstås gått lika bra med *Subversion*, eller *Git*.