# OOP1
Inför OOP1 Tentan

## Operatorer 
C# har väldigt många olika operatorer, nedan kommer alla operatorer som är relevanta inför tentan.

### Aritmetiska
* Addition (+), subtraktion (-), multiplikation (*), division (/) och modulo (%)
* Mulitplikation (*), subtraktion (/) och modulus (%) binder starkare än + och -, dvs 3+2*4 = 3+(2*4)

### Relation
Följande operatorer kan användas för att jämföra två olika värden. Viktigt att notera är att likhetstecknet alltid ska ligga till höger om det andra tecknet.

* >  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Större än
* <  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Mindre än
* == &nbsp;&nbsp;&nbsp;&nbsp; Lika med
* != &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Inte lika med/skilt från
* <= &nbsp;&nbsp;&nbsp;&nbsp; Mindre än eller lika med
* >= &nbsp;&nbsp;&nbsp;&nbsp; Större än eller lika med

Exempel på relations operatorer:
```c#
if(2 > 1) // => True därför 2 är STÖRRE än 1
if(2 < 1) // => True därför 1 är MINDRE än 2
if(2 == 1) // => False därför att 2 inte är samma som 1
if(2 != 1) // => True därför att 2 inte är samma som 1
if(3 <= 2) // => True därför att 2 är mindre än eller lika med 3
if(2 >= 1) // => True därför att 2 är större än eller lika med 1
```

### Logiska operatorer
* && &nbsp;&nbsp; Och
* || &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Eller
* ! &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Negation

Exempel på logiska operatorer:
```c#
if(true && true) // => True därför att båda påståenden är sanna
if(true || false) // => True därför att ett av påståenden är sant
if(!true) // => False därför negationen av true är false
```

### Inkrementering och dekrementering
```c#
int number = 1; // variabeln number tilldelas värdet 1
number++; // variabeln number ökar/inkrementeras med 1
number += 5 // variabeln number ökar med 5
number *= 3 // variabeln number ökar med sitt värde multiplicerat med 3
number /=2 // variabeln number subtraheras med 2
```

## Selektion
Det finns två typer av selektion i språket c#, if och switch.

### Satsen if
* Villkor med relationsoperatorer eller logiska operatorer
* Exempelvis > (större än)

Se exempel på if-satser under logiska operatorer och relations operatorer.


### Satsen Switch
* Vilken case-sats som körs beror på villkoret
* Fördelaktigt över if-satser när jämförelse sker mot många olika utfall

Exempel på switch:
```c#
switch(nummer) // Värdet variabeln antar avgör vilken case-sats som ska köras
{
  case 1:
    //ifall nummer = 1 körs denna kod;
  break;
  case 2:
    //ifall nummer = 2 körs denna kod;
  break;
  default:
    //ifall nummer är något annat körs denna kod;
  break;
}

switch(nummer) // Switch kan även köra samma kod för ett antal olika cases
{
  case 1:
  case 2:
  case 3:
  case 4:
    // Ifall nummer är lika med 1, 2, 3 eller 4 så körs denna kod.
  break;
  default:
    //ifall nummer är något annat körs denna kod;
  break;
}
```

## Iteration
Iteration används för att återupprepa ett kodblock flera gånger, detta kan göras genom for-loopar eller while-loopar.
En for loop körs ett givet antal iterationer, t ex 10 gånger medan en while loop körs så länge ett påstående är sant.
Om en for loop inte har ett givet antal iterationer eller en while loops påstående alltid förblir sant kommer loopen pågå
"för alltid" och då få programmet att krascha.

Exempel på loopar
```c#
for (int i = 1; i <= 10; i++) // Körs tio gånger
while (i == 5) // Körs så länge i är like med 5
```

## Datatyper

### Värde/Primitiva datatyper
Primitiva datatyper sparas direkt i c# stack och dess värden är direkt nåbara i ett program.
Eftersom att värdet av en primitiv datatyp är direkt nåbart kan man enkelt kopiera eller byta ut dem.

* Kan inte delas ner i mindre komponenter.
* Kan bara presentera ett värde.
* Har ingen inre struktur eller metoder utan kan bara påverkas av yttre operatorer. 

```c#
int tal1 = 2;
int tal2 = 4;

tal1 = tal2;
// Värdet av tal1 byts ut mot värdet av tal2.
```


#### int
```c#
int helTal = 2;
// Int är datatypen för heltal, kan endast innehålla heltal och inga decimaler.
// Vid matematiska operationer med inttal så kommer summan att avrundas till närmsta heltal
```

#### bool
```c#
bool santEllerFalskt = true;
// Boolean kan endast vara true eller false
```

#### float
```c#
float flytTal = 1.2323f;
// Flyttal är ett tal med decimaler och kan hålla ett stort antal siffror. Vid användning av float måste man alltid avsluta talet med f.
// Om man inte avslutar talet med f så kommer c# hantera talet som en double
```

#### double
```c#
double dubbeltSåStortFlyttal = 1.232323232;
// En double är exakt som en float ett tal som kan hålla decimaler.
// Skillnaden mot en float är att en double kan hålla dubbelt så många bitar som en float.
```

#### string
```c#
string sträng = "Jag är en sträng";
// En sträng kan hålla vilka tecken och bokstäver som helst mellan sina dubbla citationstecken.
// Just dem dubbla citationsteckna "" är viktiga då de inte får förknipas med en char som har enkla citationstecken ''
// En sträng är i grunden en array av chars.
```

#### char
```c#
char tecken = 't';
// Enbart en karaktär, måste alltid omslutas av enkla citationstecken ''
```

### Referenstyper
Referenstypers värde sparas direkt på stacken men nås genom en identifierare på heapen.
Alltså kan man aldrig direkt nå en referenstyps värde utan endast dess identifierare, det själva underliggande värdet
hanteras av .NET plattformen. Detta gör att man endast kan påverka referenstypens identifierare i efterhand och inte det 
underliggande värdet.

```c#
string[] array1 = new string[3]{"Sträng nr1", "Sträng nr2", "Sträng nr3"};
string[] array2 = array1;
array2[0] = "Uppdaterat sträng nr1";

Console.WriteLine(array1[0]); // => "Uppdaterad sträng nr1"
Console.WriteLine(array2[0]); //2 => "Uppdaterad sträng nr1"
// Trots att vi endast ändrar det första värdet av array2 så ändras ändå värdet för de båda arrayerna.
// Detta beror på att båda arrayerna har samma identifierare på stacken som vid ändring kommer att peka på ett nytt värde på heapen.
```

#### Array
```c#
string[] arrayAvSträngar = new string[3]{"Sträng nr1", "Sträng nr2", "Sträng nr3"};
int[] arrayAvInts = new int[2]{20, 30};

Console.WriteLine(arrayAvSträngar[0]); // => "Sträng nr1"
Console.WriteLine(arrayAvInts[1]); // => 30
// En array kan hålla flera värden av samma datatyp, t ex strängar eller ints som här ovan.
// Antal värden i en array måste definieras vid deklaration och kan inte ändras i efterhand.
// Värdena i en array ligger på positioner som kallas index, första positionen i en array är alltid 0.
```

#### List
```c#
ArrayList<string> listaAvSträngar = new ArrayList<string>{"Sträng nr1", "Sträng nr2", "Sträng nr3"};
ArrayList<int> listaAvInts = new ArrayList<int>{20, 30};

Console.WriteLine(listaAvSträngar[0]); // => "Sträng nr1"
Console.WriteLine(listaAvInts[1]); // => 30
// En lista fungerar på många sätt likt en array men är lite mer dynamiskt.
// Man behöver inte definiera antalet föremål i en lista vid deklaration och antalet föremål kan även ändras i efterhand.
```

## Typomvandling och konvertering
* Typomvandling och konvertering är inte samma sak.
* Typomvandling görs enbart mellan datatyper som är väldigt lika, t ex: int och double
* Konvertering kan göras av datatyper som skiljer sig från varandra t ex en string till en int, string -> int ”7” -> 7

### Konvertering

```c#
string sträng1 = ”12.3”;
string sträng2 = ”567”;
string sträng3 = ”en sträng”;

// Konverterar en sträng till en double
double d = Convert.ToDouble(sträng1); // d = 12.3

// Konverterar en sträng till en int
int i = Convert.ToInt32(sträng2); //i = 567

// Försöker konvertera en sträng utan siffror till en int, men kommer att misslyckas och krascha programmatet
int i = Convert.ToInt32(sträng3); // Kommer att skicka en exception
```

### Implicita typomvandlingar
Implicita typomvandlingar sker utan informationsförlust.
```c#
int i = 33;
double d = i; //d = 33.0
// Typomvandlingen sker utan informationsförlust, därav är det en implicit typomvandling
```

### Explicita typomvandlingar
Explicita typomvandlingar sker med informationsförlust.
```c#
d = 3.5;
i =(int)d; //i = 3
// Typomvandlingen sker med informationsförlust, därför är det en explicit typomvandling
```

## Klasser
En klass är en typ av datastruktur som kan hålla variabler, metoder, mm..

```c#
// Klasser kan vara antingen public, private eller protected.
// En public class kan anropas i hela programmet.
// En private class kan endast anropas innanför klassen själv.
// En protected class kan endast anropas innanför klassen själv eller klasser som ärver av den.
public Class klassNamn {
}
```

### Instansvariablar
```c#
// Precis som klasser kan man på liknande sätt använda public, private och protected för instansvariabler
public string enPublikSträng = "Jag kan nås överallt i klassen och i alla instanser av klassen!";
private string enPrivatSträng = "Jag kan endast nås innanför klassen";
protected string enSkyddadSträng = "Jag kan endast nås innanför klassen eller inom alla klasser som ärver av denna!";
```

### Metoder
```c#
// Metoder kan returnera alla datatyper och/eller ta emot dem som argument.
// Om en metod inte returnerar något använder man sig utav void.
// Om en metod inte tar emot några argument så lämnar man bara paranteserna efter metodnamnet tomma.
private void metodNamn(int heltal){
  Console.WriteLine("En privat metod som inte returnerar någonting utan bara skriver ut följande heltal: " + heltal);
}
```

### Konstruktorn
```c#
// Samma sak gäller även metoder och konstruktorn som också kan använda public, private och protected
// Alla klasser har alltid en konstruktor, antingen som vi själva definerar eller defineras automatiskt vid kompilering.
// En konstruktor ser precis ut som en metod förutom att den inte har ett returvärde och alltid har samma namn som klassen.
// Konstruktorn körs automatist vid instantiering av klassen
public klassNamn(){
  Console.WriteLine("Jag är en konstruktor!");
}
```

## Objektorienterad programmering

### Abstraktion
Abstraktion är ett sätt att hantera något komplext och bryta ner det till mer lättförståliga element. När man tänker på abstraktioner inom programmering läggs vikten på dess funktionalitet och beteende istället för hur de tekniskt ska implementeras.

### Inkapsling
Inkapsling innebär att man begränsar åtkomst till ett objekts medlemmar och data. Genom att använda sig av inkapsling kan man skydda koden från felaktigt användande och oväntade förändringar av data.
