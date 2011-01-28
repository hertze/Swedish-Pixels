--- 
title:      Markdown framför Textile
created_at: 2008-04-25 15:14:00.791401 +01:00
keywords: 
filter:     markdown  
description: Joakim Hertze skriver på webben
layout:     post
---
doc_prefix: c2008-04-25

Sedan 2003 har jag använt mig av _Dean Allens_ [Textile][][^1] när jag publicerar inlägg på den här bloggen. Först till mitt egenhändigt kodade publiceringssystem, men senare som en del av en vanlig TextPattern-installation. Jag tyckte det var ett underbart finurligt sätt att märka texten, utan att själv behöva skriva XHTML taggar.

Jag såg att det fanns ett alternativ i _John Grubers_ [Markdown][], men tyckte det verkade alltför krångligt att lära sig en ny syntax. Dessutom gick det inte heller att med någon enkelthet knyta detta till mitt publiceringssystem.

Alldeles nyligen kastade jag ett nytt öga på Markdown och såg plötsligt det Gruber själv angett som dess största förtjänst, nämligen dess läsbarhet. 

Studera följande exempel. Jag vill åstadkomma följande XHTML-snipplet, som innehåller en rubrik, några stycken, en lista, två länkar och en _blockquote_:

	<h1>Strindberg</h1>

	<p>Johan August Strindberg var en 
	<a href="http://strindberg.net">svensk författare</a>
	och bildkonstnär (målare). Han räknas som en av Sveriges
	mest betydelsefulla författare. Internationellt är han
	främst känd som dramatiker.</p>

	<ol>
		<li>Ett alternativ</li>
		<li>Ett andra alternativ</li>
		<li>Ett tredje alternativ</li>
	</ol>

	<blockquote>
		<p>Under fyra decennier var Strindberg en 
		<a href="http://mumindalen.nu">dominerande gestalt</a>
		i det litterära Sverige. Han var ständigt omdiskuterad
		och ofta involverad i personliga konflikter. Hans verk
		innehåller ett flertal romaner, noveller och dramer som
		räknas som klassiker inom svensk litteratur.</p>
	</blockquote>

För att åstadkomma detta med Textile skriver man följande:

	h1. Strindberg

	Johan August Strindberg var en 
	"svensk författare":http://strindberg.net
	och bildkonstnär (målare). Han räknas som en av Sveriges
	mest betydelsefulla författare. Internationellt är han
	främst känd som dramatiker.

	# Ett alternativ
	# Ett andra alternativ
	# Ett tredje alternativ

	bq. Under fyra decennier var Strindberg en 
	"dominerande gestalt":http://mumindalen.nu i det 
	litterära Sverige. Han var ständigt omdiskuterad
	och ofta involverad i personliga konflikter. Hans verk
	innehåller ett flertal romaner, noveller och dramer som
	räknas som klassiker inom svensk litteratur.

För att åstadkomma samma sak med Markdown skriver man:

	Strindberg
	==========

	Johan August Strindberg var en [svensk författare][]
	och bildkonstnär (målare). Han räknas som en av Sveriges
	mest betydelsefulla författare. Internationellt är han
	främst känd som dramatiker.

	1. Ett alternativ
	2. Ett andra alternativ
	3. Ett tredje alternativ

	> Under fyra decennier var Strindberg en 
	> [dominerande gestalt][] i det litterära Sverige. Han var
	> ständigt omdiskuterad och ofta involverad i personliga
	> konflikter. Hans verk innehåller ett flertal romaner,
	> noveller och dramer som räknas som klassiker inom svensk
	> litteratur.

	[svensk författare]: http://strindberg.net
	[dominerande gestalt]: http://mumindalen.nu
	
Egentligen är skillnaderna kanske inte så stora, men om man jämför exemplen ser man en sak: Textile-dokumentet ser ut att vara uppmärkt med taggar (om än mindre obtrusivt än rena HTML-taggar), medan Markdown-dokumentet ser ut som förnuftigt formatterad ren text. I Markdown kan man dessutom lägga länkadresserna _utanför_ sin text, vilket ytterligare ökar läsbarheten.

Det här tycker jag är kittlande: Om man skriver sin text i en texteditor och formger den så den blir så läsbar som möjligt så är chanserna stora att Markdown kan omvandla den till giltig XHTML. Gruber hade rätt, besservisser som han är.

Jag har nu bytt från Textile till Markdown[^2] i min TextPattern-installation, vilket ännu så länge innebär ett hack. När väl TextPattern 4.1.0 kommer ut (om det blir under min livstid låter jag vara osagt) lär det ha stöd för villket "text till XHTML"-vertyg som helst.

[textile]: http://textile.thresholdstate.com/

[markdown]: http://daringfireball.net/projects/markdown/

[^1]: Textile utvecklas inte längre av Dean Allen, utan är en del av TextPattern. Porteringar existerar dock även till andra plattformar.

[^2]: Egentligen [PHP Markdown](http://michelf.com/projects/php-markdown/), en portering från Perl till PHP av _Michel Fortin_.