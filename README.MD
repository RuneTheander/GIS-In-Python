|  SYSTEM OVERSIGT |                                  |   
|------------------|----------------------------------|
| System Navn             | Adhoc Opgave | 
| Filnavn Navn             | HøjspændingOver.ipynb |      
| Sprog (Biblioteker)            | Python ( cx_Oracle, sqlalchemy, shapely, pandas, geo pandas, openpyxl, glob, os, datetime, ast )                           |  
| Beskrivelse og formål     |Dette Script retter de objekter som løber under højspændingsledningerne således at de passer på reglen: Højspænding skal krydse > 5 meter over andre objekter|   
| Input             | Fejlliste fra Kurt (C:/Users/B177999/Desktop/Fejlsteder.xlsx)  + GEODANMARK_60_NOHIST.(Alle GEODK Objektyper)|     
| Output            |  Alle de rettede Objekter som løb mindre end 5 meter under en eller flere Højspændingsledninger             |    
| Output Path       | C:/Users/b177999/Desktop/Hoejspaending_over_under/                   |    
|  forbindelser til databaser og drev          | oracle database: 'GEOBANK.prod.sitad.dk' |   
|  Udvikler          |  Rune Theander (Geo)                                 |   
|  Status          | Ikke i brug                          |     
