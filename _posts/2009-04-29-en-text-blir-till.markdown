--- 
title:       En text blir till
created_at:  2009-04-29 14:45:23.791401 +01:00
keywords:    skriva, skrivverktyg, semantisk, texteditor, Ulysses, TextMate
description: Jag förespråkar ett semantiskt arbetssätt medan man skriver. Det betyder att man bestämmer vilken funktion ett textavsnitt skall ha, snarare än att bestämma hur det skall se ut.  
layout:      post
---

![TextMate med förhandsgranskning][6]

När jag författar en text arbetar jag enligt följande schema:

1. Idésamlande
2. Utkast
3. Korrekturläsning
4. Revidering

När jag samlar idéer använder jag oftast penna och papper, eftersom det släpper min tanke fri. Någon gång gör jag en disposition på det här stadiet, men i allmänhet är jag för lat för det. Utkastet skriver jag i min texteditor, men jag behöver sedan skriva ut texten för att korrekturläsa den. Av hänsyn till naturen har jag försökt hoppa över utskrifterna, men jag måste se svärtan mot pappret och jag behöver stryka, ändra och stuva om med rödpenna. När det är dags för revidering återvänder jag till texteditorn. Jag upprepar steg två till fyra minst tre gånger. Först tittar jag på innehåll och struktur, sedan på ordval och meningsbyggnad och sist stryker jag bort onödigt fluff.

Jag förespråkar ett semantiskt arbetssätt medan man skriver. Det betyder att man bestämmer vilken funktion ett textavsnitt skall ha, snarare än att bestämma hur det skall se ut. En mening kan exempelvis vara en *rubrik*, inte en samling tecken satta i 24-punkters Garamond.

De texter jag skriver publiceras antingen som en PDF ämnat för utskrift, eller som hypertext ämnat för webben.

Om texten är ämnad för webben, till exempel Swedish Pixels, använder jag nästan enbart *Macromates* [TextMate][1]. Jag skriver mina alster som rena textfiler i skrivformatet [Markdown][2] och de omvandlas sedan till XHTML av mitt publiceringssystem. Jag använder även TextMate för kortare saker ämnat för utskrift, som brev och resuméer. Med hjälp av *Fletcher T. Penneys* [MultiMarkdown][5] omvandlas Markdown-uppmärkt text till LaTeX, som sedan typsätts till PDF.

TextMate är en förträfflig texteditor, som med några enkla inställningar kan förhandsvisa Markdown-uppmärkt text som renderad XHTML. Först och främst är det en editor skapad för för programmerare och jag saknar en del funktioner som underlättar kreativt skrivande. Man kan inte använda proportionerliga typsnitt och det går inte heller att ställa in textens radhöjd eller avståndet mellan stycken. Det finns inget fullskärmsläge och det saknas bra verktyg för att organisera längre dokument.

Om jag skriver längre alster för tryck eller utskrift använder jag nästa uteslutande *The Soulmen's (tidigare Blue-Tec)* [Ulysses][3]. Det är en semantisk texteditor, med bättre organisatoriska förmågor. Ulysses är enligt mitt tycke det överlägset bästa skrivverktyget för prosa, även om det finns en del brister. Projekthanteringen är onödigt komplicerad och det är svårt att använda programmet tillsammans med mjukvara för versionsskontroll, som SubVersion. Tyvärr saknas också möjligheten att förhandsvisa text som XHTML, vilket gör programmet olämpligt för webbtexter.

Texter skrivna i Ulysses kan exporteras till en rad olika format, men jag väljer oftast LaTeX. Jag använder TextMate för att finjustera LaTeX-filerna och sedan typsätta dem till PDF.

Jag inser att mitt arbetssätt kan framstå som onödigt komplicerat och en smula nördigt. Det har dock tjänat mig väl och jag rekommenderar alla som skriver att prova den semantiska metoden. Till och med *Microsoft Word* och [Apple Pages][4] stöder den, även om det känns som att gå över ån efter vatten.

[1]: http://macromates.com
[2]: http://daringfireball.net/projects/markdown/
[3]: http://www.blue-tec.com/ulysses/
[4]: http://www.apple.com/iwork/pages/
[5]: http://fletcherpenney.net/multimarkdown/
[6]: http://swedishpixels.com/bilder/textmate-preview.jpg