--- 
title:      Installera Markdown för TextPattern
created_at: 2008-12-07 08:10:51.791401 +01:00
keywords:   markdown, textpattern
filter:     markdown
description: Joakim Hertze skriver på webben
layout:     post
---
doc_prefix: c2008-12-07

Jag uppgraderade nyligen till TextPattern 4.0.7 och som alltid fick den processen mig att ifrågasätta alla de tillägg och modifieringar jag gjort av min installation. I sådana här lägen är det alltid skönare om man har begränsat sig till _out of the box_-versionen, eftersom varje ändring och tillägg måste göras om. Man vet ju aldrig heller om något _plugin_ slutar fungera. I mitt fall var det ett som behövde uppgraderas för den nya versionen, men det gick på en dag tack vara en lyssnade pluginskapare.

En av de viktigare modifieringarna jag gjort är att ersätta _Textile_ med _Markdown_. Skälen till detta har jag skrivit om i [ett tidigare inlägg] [1]. Här kommer flödesschemat för den processen, som en framtida referens för mig själv -- eller för någon annan behövande.

1. Ladda ner [PHP Markdown Extra] [2] och [PHP SmartyPants Typographer] [3]. De finns även i vanliga versioner (det vill säga PHP Markdown och PHP SmartyPants) men dessa två innehåller en del nyttiga extra funktioner, framför allt fotnoter och konfigurerbar interpunktation.

2. Starta ditt FTP-program och logga in på ditt konto. Navigera till mappen `/textpatten/lib` och byt namn på filen `classTextile.php` (förslagsvis till `classTextile_backup.php`).

3. Gå till din nerladdningsmapp. Packa upp de två paket du laddat ner i steg 1. Döp om `markdown.php` till `classTextile.php`.

4. Öppna filen `classTextile.php` i din texteditor. Navigera ner till funktionen `Markdown_Parser`, som finns på rad 230. Lägg till koden `$this->fn_id_prefix = uniqid(rand());` på raden efter kommentarerna. Efteråt skall det se ut så här:

		function Markdown_Parser() {
		#
		# Constructor function. Initialize appropriate member variables.
		#
			$this->fn_id_prefix = uniqid(rand());
			$this->_initDetab();
			$this->prepareItalicsAndBold();
		...

	Detta steg är nödvändigt för att fotnoter skall genereras med unika identifierare. Utan dessa är risken stor att du får fotnoter med samma namn om du publicerar flera artiklar på en och samma sida. Jag kan inte lova att detta är det bästa sättet att lösa problemet. Jag kontaktade upphovsmannen till PHP Markdown, men har inte fått något svar. Ovanstående kod är resultatet av Google-sökningar och _trial-and-error_.

5. Öppna filen `smartypants.php` i din texteditor. Justera inställningarna efter ditt språk. Framför allt gäller det citattecken på rad 30 och 31.

6. Ladda upp _både_ `classTextile.php` (som ju egentligen är markdown-filen) och `smartypants.php` till mappen `/textpatten/lib` på din server.

7. Logga in i din TextPattern-installation. Klicka på fliken _Admin_ och därefter på underfliken _Språk_. Välj _Engelska_ (brittisk engelska eller amerikanska). Spara. Klicka på underfliken _Advanced_. Se till att alternativet _Allow more Textile markup?_, under _Comments_, är satt till _yes_. Spara. Gå tillbaka till spåkfliken och välj svenska igen. Spara. Nu kan man använda Markdown även när man skriver kommentarer på din sajt.

Klart.


[1]: http://www.hertze.com/blogg/2008/04/markdown-framfoer-textile/
[2]: http://michelf.com/projects/php-markdown/extra/
[3]: http://michelf.com/projects/php-smartypants/

