# Att hantera gamla studenters nya resultat med Kth:s datasystem

En gammal student (student från tidigare kursomgång) har redovisat en laboration i kursen programmeringsparadigm. Det som borde hända är att kursledaren får en notis om att en student är klar med kursen och kan skicka in dessa resultat till LADOK. Studenten mailar typiskt mig och berättar att hen vill ha sina poäng för att få behålla studentbostad, CSN eller liknande.

När vi hade rapp så skulle (1) tidigare års delresultat ha överförts till årets kursomgång och (2) om detta delresultat resulterade i att ett ladokmoment blev klart så skulle Rapp ha räknat ut detta och vi kunde direkt skicka vidare detta till Ladok.

Numera ligger tidigare års resultat kvar i gamla kursomgångar på Canvas, så det är teoretiskt möjligt att en student har sina delresultat utspridda över tre olika kursomgångar. För att lösa detta behöver jag ett separat system som räknar ihop tidigare års ofärdiga delresultat och det programmet behöver jag skriva själv.

Problemet med att skriva program själv som hämtar ut saker ur Canvas är att Canvas inte har ett API som låter mig be om min CSV-fil med delresultat utan jag blir tvungen att använda webbgränssnittet som har en 90 sekunders väntetid på att generera en .CSV-fil. Det innebär att om jag vill ha en dashboard som kontinuerligt visar studenters delresultat, något som inte stöds av Canvas, så behöver jag dels programera systemet själv, dels vänta 90 sekunder på en ny fil varje gång som jag vill uppdatera dashboarden.

Eftersom det här är såpass besvärligt så gör jag det mycket sällan och medans jag väntar så mailar studenter mig om att deras resultat inte finns innne ännu.

Nu kommer vi till punkt (2) som rapp gjorde förut. Jag behöver räkna ihop alla delresultat för att se om någon eventuellt har klarat av ett moment i kursen. Om någon har gjort det så får ett annat system som jag har skrivit själv addera delresultaten och generera en excelfil som jag skickar till education support.

# Från delmoment till färdiga kurser

När delmomenten är klara från kursens sida så skickas en lista till Education Support som matar in listan manuellt i Ladok. Det kan bli fel. Det kan ta tid. Även om det går snabbt och blir rätt så blir det enbart delmomenten som blir inrapporterade och inte hela kursen. Om det tar tid eller blir fel så får jag som kursledaren ännu fler mail under väntan.

# Att rätta tentor

Med ett moderns system skulle studenternas tentor scannas, rättarna får tentorna levererade digitalt till sina datorer och kan skriva kommentarer och mata in resultat i ett webbgränssnitt helt utan att behöva se de fysiska tentorna.

Istället får tentorna rättas manuellt från papper. Om 50 studenter har gjort ungefär samma fel och vi vill ge feedback på det felet så blir vi tvungna att skriva det för hand på 50 tentor istället för att kopiera och klistra in det från en digital mall med standardkommentarer, vilket vi kan göra när vi rättar digitalt.

Betygen behöver dels fyllas i på papperen, men trots att Scannern stödjer att läsa ett G som godkänt och teoretiskt sett borde kunna överföra alla tentaresultat till systemet, men vi behöver dessutom manuellt mata in alla resultat i ett Excelark som skickas till education support som matar in det i LADOK, manuellt igen.

# En student är klar med en labb och vill redovisa

En student har fått godkänt på en laboration i Kattis och vill boka ett redovisningstillfälle. Många kurser har då schemalagda redovisningspass där studenter kan gå och köa i en timme tills det kommer en assistent. Det ger stress och fungerar dåligt.

Ett annat alternativ är att använda REMORES, ett gammalt krångligt hack som låter studenterna boka in sig på labbtider för en assistent. När det här fungerar så slipper vi köer, men det här är ett krångligt Hack som kräver tid för kursledare att sätta sig in i.

Ett tredje alternativ är att ha en separat server som pratar med Github och hanterar delresultat och bokning den vägen. Det är vad vi gör i progp och det fungerar, men det krävs en hel del av oss som kursledare för att programmera och sköta en server.
