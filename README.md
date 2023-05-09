# LINQDb
## Creazione progetto .NET
###### Dopo aver aperto la cartella su VisualStudio Code aprire un nuovo terminale e digitare : 
``` 
dotnet new console 
```
![image](https://github.com/P4020/LINQDb/assets/117436985/b79a9091-6bf9-43cc-89df-d00b2f404f03)
###### Per far funzionare al meglio il codice digitare nel terminale la senguente riga di codice per la libreria SQL:
``` 
dotnet add package sqlite-net-pcl
```
###### Inoltre scaricare l'estensione SQL VIEWER per visualizzare tutto il database del file chinook.db su VisualStudio Code.

![image](https://github.com/P4020/LINQDb/assets/117436985/b3e68d01-2da1-49a9-a25b-009edbe6bdf6)

## Dove trovare il file db chinook.db
###### Il link per scaricare il file db chinook.db è : 

https://www.sqlitetutorial.net/sqlite-sample-database/#:~:text=the%20following%20link.-,Download%20SQLite%20sample%20database,-In%20case%20you

###### Appena entrati nel sito scaricare il file dal link evidenziato!

## Codice C#
###### Per la visualizzazione degli artisti e dei loro nomi utilizzare il seguente programma :
``` 
using SQLite;

SQLiteConnection cn1 = new SQLiteConnection("chinook.db");
var tblArtists = cn1.Query<Artist>("select * from artists");
Console.WriteLine($"In questa tabella ci sono {tblArtists.Count} record!");

tblArtists = tblArtists.OrderByDescending(x=>x.Name).ToList();
foreach(var artista in tblArtists)
{
    Console.WriteLine($"{artista.Name}");
}

public class Artist
{
    public int ArtistId{get;set;}
    public string Name{get;set;}
}
```

