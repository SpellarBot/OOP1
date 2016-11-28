```c#
public void Anagram(string input1, string input2)
{
    input1 = input1.ToLower(); // gör om till gemener
    input2 = input2.ToLower(); // gör om till gemener
    int antalKorrektaTecken = 0; // deklaration av variabel som kommer representera summan av likadana tecken
    bool Anagram = false; // bool som avgör om anagram finns
    string letters = ""; //deklarerar en tom sträng 
    int index = 0; //deklarerar en int och sätter värdet till 0

    string[] seperateWords = input1.Split(' '); //splittar input med hjälp av metoden split till en array av flera strängar

    for (int i = 0; i < seperateWords.Length; i++) // Vi kontrollerar om det finns anagram varje ord för sig genom iteration
    {
        letters = seperateWords[i]; //Vi sätter letters till samma ord som det vi just nu itererar av seperateWords
            for (int j = 0; j < input2.Length; j++) // Vi kontrollerar varje tecken i input2 för sig genom iteration
            {
                if (seperateWords[i].IndexOf(input2[j]) != -1) //Genom IndexOf metod kontrollerar vi om första tecknet i input2 finns i det aktuella seperateWords ordet
                {
                    index = seperateWords[i].IndexOf(input2[j]); //index får det startvärde den bokstav vi undersöker i input2 har

                    if(letters.IndexOf(input2[j]) != -1) //Här kontrolleras om det fortfarande finns en bokstav av input2[j]s karaktär kvar i letters
                    {
                    letters = seperateWords[i].Remove(index, 1); //tar bort bokstaven den aktuella bokstaven från letters
                    antalKorrektaTecken++; //Lägger till 1 till antalKorrektaTecken
                    }        
                }      
            }
                if (antalKorrektaTecken == input2.Length && input2.Length == seperateWords[i].Length) //Kontrollerar att antalet korrekta tecken är samma som input2s längd och att inputs längd är lika lång som det ord som itereras längd
                {
                    Console.Write(seperateWords[i] + " "); // Anagramet skrivs ut
                    antalKorrektaTecken = 0; // Nollställer antalKorrektaTecken inför nästa ord i seperateWords
                    Anagram = true; // Vi har ett anagram och boolen anagram sätts till sann
                }
    }
    if (Anagram == false) // Om vi fortfarande inte har några anagram efter att samtliga ord loopats är anagram variabeln falsk och nedanstånde skrivs ut
    {
        Console.WriteLine("Inga anagram finns");
    }
}
```
