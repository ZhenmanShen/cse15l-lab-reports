# Lab 3 Report (grep command)
## grep -i
`i` or `--ignore-case` performs a case insensitive search in a given file. It returns the first context in which the string or pattern appears.
Source: ChatGPT and [geeksforgeeks.org](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
1. The command search for any string that contains `is` and print the context during its appearance. In this case, `is` is apart of `listed`. 
```
zhenmanshen@Zhenmans-MacBook-Pro berlitz1 % grep -i "is" HandRHongKong.txt
        Hotels listed below have full air-conditioning, offer 24-hour or
        summer and at Christmas. If you do arrive without making advance
        occupancy, with bath or shower. Unless otherwise noted, hotels take all
```

2. The command search for any string that contains the pattern `the` and print the context during its appearance. In this case, `the` is part of 
```
zhenmanshen@Zhenmans-MacBook-Pro berlitz1 % grep -i "the" HandRHongKong.txt
        Hong Kong has some of the most luxurious hotels in the
        world, with representatives from all the major international chains.
        arrangements, the Hong Kong Hotel Reservation Center at the
        As a basic guide, the symbols below have been used to
        occupancy, with bath or shower. Unless otherwise noted, hotels take all
        added to the bill.
```

## grep -l
`l` or `--files-witch-matches` performs a print function of all the files that includes a given string or pattern. However, it doesn't include where the string or pattern in the file(s) since it only displays the name of the file(s).
Source: ChatGPT and [geeksforgeeks.org](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
1. The command search for a given input, in this case it is `the`. If it appears in the text, then it would print out the name of the text file. 
```
zhenmanshen@Zhenmans-MacBook-Pro berlitz1 % grep -l "the" HandRHongKong.txt
HandRHongKong.txt
```
2. The command search for a given input, in this case it is `History`. If it appears in the text, then it would print out the name of the text file.
```
zhenmanshen@Zhenmans-MacBook-Pro berlitz1 % grep -l "history" HistoryIsrael.txt HandRHongKong.txt
HistoryIsrael.txt
```

## grep -r
`r` or `--recursive` performs a recursive function which that search through all files in a directory for a given string or pattern.
Source: ChatGPT and [geeksforgeeks.org](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
1. The command performs a recursive search through all the files in the directory `travel_guides` for the term `History`. Adding `-l` to the and displays all the text files that includes the term `History`. 
```
zhenmanshen@Zhenmans-MacBook-Pro written_2 % grep -r -l "History" travel_guides
travel_guides/berlitz1/HistoryJapan.txt
travel_guides/berlitz1/IntroMalaysia.txt
travel_guides/berlitz1/HistoryJamaica.txt
travel_guides/berlitz1/HistoryEgypt.txt
travel_guides/berlitz1/HistoryIsrael.txt
travel_guides/berlitz1/WhereToLakeDistrict.txt
travel_guides/berlitz1/HistoryDublin.txt
travel_guides/berlitz1/HistoryMallorca.txt
travel_guides/berlitz1/HistoryJerusalem.txt
travel_guides/berlitz1/HistoryHongKong.txt
travel_guides/berlitz1/HistoryIstanbul.txt
travel_guides/berlitz1/WhereToItaly.txt
travel_guides/berlitz1/HistoryLasVegas.txt
travel_guides/berlitz1/HistoryGreek.txt
travel_guides/berlitz1/WhereToMalaysia.txt
travel_guides/berlitz1/HistoryHawaii.txt
travel_guides/berlitz1/HistoryMadeira.txt
travel_guides/berlitz1/WhereToDublin.txt
travel_guides/berlitz1/HistoryMalaysia.txt
travel_guides/berlitz1/WhereToLosAngeles.txt
travel_guides/berlitz1/HistoryIbiza.txt
travel_guides/berlitz1/HistoryEdinburgh.txt
travel_guides/berlitz1/HistoryFWI.txt
travel_guides/berlitz1/HistoryLakeDistrict.txt
travel_guides/berlitz1/WhereToJerusalem.txt
travel_guides/berlitz1/WhatToJamaica.txt
travel_guides/berlitz1/WhereToHongKong.txt
travel_guides/berlitz1/WhereToFWI.txt
travel_guides/berlitz1/WhereToIstanbul.txt
travel_guides/berlitz1/WhatToLosAngeles.txt
travel_guides/berlitz2/Portugal-History.txt
travel_guides/berlitz2/Berlin-WhereToGo.txt
travel_guides/berlitz2/Costa-History.txt
travel_guides/berlitz2/Barcelona-History.txt
travel_guides/berlitz2/Boston-WhereToGo.txt
travel_guides/berlitz2/California-WhereToGo.txt
travel_guides/berlitz2/Berlin-History.txt
travel_guides/berlitz2/Bali-History.txt
travel_guides/berlitz2/Crete-WhereToGo.txt
travel_guides/berlitz2/Athens-History.txt
travel_guides/berlitz2/Canada-WhereToGo.txt
travel_guides/berlitz2/Budapest-WhereoGo.txt
travel_guides/berlitz2/Barcelona-WhereToGo.txt
travel_guides/berlitz2/China-WhereToGo.txt
travel_guides/berlitz2/California-History.txt
travel_guides/berlitz2/Vallarta-History.txt
travel_guides/berlitz2/Budapest-WhatToDo.txt
travel_guides/berlitz2/Cancun-History.txt
travel_guides/berlitz2/CostaBlanca-History.txt
travel_guides/berlitz2/NewOrleans-History.txt
travel_guides/berlitz2/China-History.txt
travel_guides/berlitz2/Crete-History.txt
travel_guides/berlitz2/Amsterdam-History.txt
travel_guides/berlitz2/PuertoRico-WhereToGo.txt
travel_guides/berlitz2/Beijing-History.txt
travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
travel_guides/berlitz2/Bermuda-history.txt
travel_guides/berlitz2/CanaryIslands-History.txt
travel_guides/berlitz2/Algarve-History.txt
travel_guides/berlitz2/Beijing-WhereToGo.txt
travel_guides/berlitz2/Budapest-History.txt
travel_guides/berlitz2/Bermuda-WhereToGo.txt
travel_guides/berlitz2/Cuba-History.txt
travel_guides/berlitz2/Bahamas-History.txt
travel_guides/berlitz2/Cancun-WhereToGo.txt
```
2. The command performs a recursive search through all the files in the directory `travel_guides` for the term `Hong Kong`. Adding `-l` to the and displays all the text files that includes the term `Hong Kong`. 

```
zhenmanshen@Zhenmans-MacBook-Pro written_2 % grep -r -l "Hong Kong" travel_guides
travel_guides/berlitz1/HandRJamaica.txt
travel_guides/berlitz1/HandRHongKong.txt
travel_guides/berlitz1/WhereToIndia.txt
travel_guides/berlitz1/HistoryHongKong.txt
travel_guides/berlitz1/WhereToMalaysia.txt
travel_guides/berlitz1/WhatToMalaysia.txt
travel_guides/berlitz1/IntroHongKong.txt
travel_guides/berlitz1/WhatToHongKong.txt
travel_guides/berlitz1/WhereToHongKong.txt
travel_guides/berlitz2/California-WhereToGo.txt
travel_guides/berlitz2/Canada-WhereToGo.txt
travel_guides/berlitz2/China-WhereToGo.txt
travel_guides/berlitz2/China-History.txt
travel_guides/berlitz2/Beijing-WhatToDo.txt
```

## grep -n
`n` or `--line-number` performs a print function for each line number that matches the given string or pattern in a selected file.
Source: ChatGPT and [geeksforgeeks.org](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

1. The command performs a search in a file and for the pattern `Hong Kong` and returns the line number along with some contexts that pattern appears in.
```
zhenmanshen@Zhenmans-MacBook-Pro berlitz1 % grep -n "Hong Kong" HandRHongKong.txt
7:        Hong Kong has some of the most luxurious hotels in the
10:        limited room service, and a wide range of facilities. Hong Kong hotels
15:        arrangements, the Hong Kong Hotel Reservation Center at the
19:        indicate high-season rates in Hong Kong dollars, based on double
```
2. The command performs a search in a file and for the pattern `US` and returns the line number along with some contexts that pattern appears in.
```
zhenmanshen@Zhenmans-MacBook-Pro berlitz1 % grep -n "US" HandRLosAngeles.txt
11:        queen-sized beds. Breakfast is not usually included at US hotels,
```
