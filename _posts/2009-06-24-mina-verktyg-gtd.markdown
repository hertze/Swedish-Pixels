--- 
title:       Mina verktyg för GTD
created_at:  2009-06-24 12:30:05.791401 +01:00
keywords:    GTD, Things, Yojimbo, Applescript, Mindnode
description: Jag använder iCal för mina kalenderdata och Cultured Codes Things för mina åtgärdslistor. Båda dessa program synkroniserar jag mellan min Mac och min iPhone. Som digitalt "catch-all"-arkiv på min Mac använder jag Yojimbo, från Bare Bones Software.   
layout:      post
---
doc_prefix: c2009-06-24



En hörnsten i David Allens GTD är att skapa ett tillförlitligt system för påminnelser. Jag har provat en del olika varianter genom åren, inklusive helt pappersbaserade lösningar, men har nu fastnat för något jag tycker fungerar. Mitt nuvarande system består av en fysisk inkorg och ett fysiskt arkivskåp, men är i övrigt digitalt.

Jag använder *iCal* för mina kalenderdata och Cultured Codes [*Things*][1] för mina åtgärdslistor. Båda dessa program synkroniserar jag mellan min Mac och min iPhone. Som digitalt "catch-all"-arkiv på min Mac använder jag [*Yojimbo*][2], från Bare Bones Software. 

För mig personligen har ett smidigt insamlande varit en förutsättning för att överhuvudtaget komma igång med GTD. Att hela tiden dumpa allt man vill komma ihåg på ett och samma ställe ger omedelbar behovstillredställelse och den tidigaste kicken när man börjar sniffa på metoden. En grundprincip för mig har varit att minimera antalet inkorgar.

Insamlandet av analoga data sker oftast via Things på min iPhone. Den sista tiden jag provat att använda Apples egna *Röstmemo*, som ingick i iPhone OS 3.0, för snabb insamling. Jag pratar definitivt fortare än jag skriver på ett virtuellt tangentbord. Vid veckogenomgången transkriberar jag inspelningarna och lägger dem i inkorgen, eller sätter upp dem direkt på en lista.

Saker som anländer i pappersform lägger jag ibland i en fysisk inkorg på mitt skrivbord, men jag är fortfarande dålig på att tömma den regelbundet.

Digitala data, som epost, webbsidor, RSS-objekt och filer, läggs direkt i Things inkorg på min Mac. I tidigare versioner av Things var det en smula omständligt att samla in detta, så till vida att man var tvungen att använda musen. Från och med version 1.1 stöds nu Applescript, vilket har rått bot på det tillkortakommandet. Jag använder två egna skript för att skicka saker till Things och ett för att arkivera saker i Yojimbo:

1. [**Mail to Things**][6]. Detta manus körs som en regel i *Apple Mail*. När ett brev anländer till en viss adress (jag använder things@min-domän.com) läggs brevet som en uppgift i inkorgen, varefter mejlet kastas. När jag sitter med min iPhone och ser en webbsida, ett tweet, eller något i min RSS-läsare skickar jag det vidare till den ovan nämnda adressen. Nästa gång jag öppnar min mejl på datorn läggs det i Things inkorg.
2. [**Collect Your Things**][7]. Detta manus är *sammanhangskänsligt* -- när det körs gör det olika saker beroende på vilket program som är aktivt. Det kan samla in innehåll och länkar från Apple Mail, Safari, NetNewswire, Yojimbo och Finder, för att sedan lägga det som uppgifter i Things inkorg. Från andra program försöker det fånga in fönstrets titel och en länk till innehållet på hårddisken. Det använder Growl för notifieringar. Jag använder själv Red Sweaters [FastScripts][5] för att tilldela skriptet en tangentkombination -- i mitt fall F15. Collect to Things är översatt till svenska, engelska och tyska, men den svenska översättningen kommer tyvärr inte att synas förrän Things självt är översatt. Något jag hoppas kunna göra snart.
3. [**Archive in Yojimbo**][8]. Detta skript arkiverar en åtgärd från Things i Yojimbo.

Trots att man noga övervägt nyttan med varje del av Things innehåller programmet element jag tycker är onödiga, bland annat *Areas of Responsibility* och en halvbakad delegeringsfunktion. Jag har försökt att använda Areas vid något tillfälle, men det slutade bara med att jag satt och organiserade mina saker istället för att göra dem. Areas of Responsibility är ett verktyg jag använder vid mina genomgångar och de bor därför i en mindmap i [*MindNode*][4].

[1]: http://culturedcode.com/things
[2]: http://barebonessoftware.com/yojimbo
[4]: http://mindnode.com
[5]: http://www.red-sweater.com/fastscripts/
[6]: /nerladdning/Mail-Things.zip
[7]: /nerladdning/Collect-Your-Things-1-2.zip
[8]: /nerladdning/Archive-in-Yojimbo.zip