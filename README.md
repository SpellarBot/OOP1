# OOP1
Inför OOP1 Tentan

## Datatyper

### Värde/Primitiva datatyper
Primitiva datatyper sparas direkt i c# stack och dess värden är direkt nåbara i ett program.
Eftersom att värdet av en primitiv datatyp är direkt nåbart kan man enkelt kopiera eller byta ut dem.

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
Referenstypers värde sparas direkt på heapen men nås genom en identifierare på stacken.
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
