# RussianElections2021
Reformatted Data from Russian State "Elections" Information System, regarding 2021 elections to the state parliament

Original dataset was collected by Sergey Shpilkin: [https://www.facebook.com/sergey.shpilkin](https://www.facebook.com/sergey.shpilkin)

Currently includes results for federal electoral district, i.e votes for parties.

## Usage:
```python
import pandas as pd

data = pd.read_csv("https://raw.githubusercontent.com/Rexhaif/RussianElections2021/main/results_federal.csv.gz")

data.head(2)
```
|    | level      | reg            | oik                           | tik       | uik      |   num_registered_voters |   received_ballots |   given_early_voting_ballots |   given_on_site_ballots |   given_off_site_ballots |   unused_ballots |   found_off_site_ballots |   found_on_site_ballots |   incorrect_ballots |   correct_ballots |   lost_ballots |   unaccounted_ballots |   KPRF |   Zelenye |   LDPR |   Novye_Ludi |   Edinaya_Rossiya |   Spravedlivaya_Rossiya |   Yabloko |   Partiya_Rosta |   RPSS |   Kommunisty_Rossii |   Grazhdanskaya_Platforma |   Zelenaya_Alternativa |   Rodina |   Partiya_Pensionerov | url                                                                                                                                                         |
|---:|:-----------|:---------------|:------------------------------|:----------|:---------|------------------------:|-------------------:|-----------------------------:|------------------------:|-------------------------:|-----------------:|-------------------------:|------------------------:|--------------------:|------------------:|---------------:|----------------------:|-------:|----------:|-------:|-------------:|------------------:|------------------------:|----------:|----------------:|-------:|--------------------:|--------------------------:|-----------------------:|---------:|----------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  0 | ЦИК России | Алтайский край | Алтайский край – Барнаульский | Алтайская | УИК №592 |                     385 |                380 |                            0 |                     140 |                       38 |              202 |                       38 |                     140 |                   4 |               174 |              0 |                     0 |     57 |         2 |     11 |           16 |                49 |                      26 |         0 |               1 |      2 |                   4 |                         0 |                      2 |        0 |                     4 | http://www.vybory.izbirkom.ru/region/izbirkom?action=show&root=1000058&tvd=22220002523303&vrn=100100225883172&prver=0&pronetvd=null&region=22&sub_region=22 |
|  1 | ЦИК России | Алтайский край | Алтайский край – Барнаульский | Алтайская | УИК №593 |                    1515 |               1500 |                            0 |                     488 |                       81 |              931 |                       81 |                     488 |                  11 |               558 |              0 |                     0 |    189 |         8 |     43 |           46 |               174 |                      60 |         0 |               1 |      4 |                  14 |                         0 |                      2 |        3 |                    14 | http://www.vybory.izbirkom.ru/region/izbirkom?action=show&root=1000058&tvd=22220002523303&vrn=100100225883172&prver=0&pronetvd=null&region=22&sub_region=22 |

## Columns Description:
1. level - Name of chief elections board, controlling these elections.
2. reg - Name of region, i.e federal subject of Russian Federation.
3. oik - Name of electoral distric within the region.
4. tik - Name of neighbourhood (i.e geographical district) withing electoral district.
5. uik - Name (number) of local electoral board. Typically there is several apartament buildings assigned to each of the uiks, with 1000-2500 voters in average.
6. num_registered_voters - Number of people, which were registered to vote in that particular uik, at the end of the last day of elections.
7. received_ballots - number of freshly printed empty voting ballots, that were received by that uik from tik.
8. given_early_voting_ballots - number of ballots from early voters (those who decided to vote before 17.09.2021), in case there were any of them.
9. given_on_site_ballots - number of ballots, that were given to the voters for voting on-site
10. given_off_site_ballots - number of ballots, that were given to the voters for voting off-site(remote villages or voting-at-home for those who can't  come to the uik building).
11. unused_ballots - number of ballots, that were left unused after the end of the last day of elections.
12. found_off_site_ballots - number of ballots, that were found in boxes dedicated to off-site voting.
13. found_on_site_ballots - number of ballots, that were found in boxes for on-site voting.
14. incorrect_ballots - number of ballots, that were recognised as invalid (zero marks or more that one mark).
15. correct_ballots - number of ballots, that were recognised as valid (exactly one mark).
16. lost_ballots - number of ballots, that were not given to voters, but also not found in unused ballots, so they are considered as lost by the uik.
17. unaccounted_ballots - number of ballots, that were received from tik, but not accounted as `received_ballots`. It happens when tik accidentally gives more ballots than it expects.
18. KPRF - number of votes for "Communist Party of Russian Federation" [http://cprf.ru](http://cprf.ru)
19. Zelenye - number of votes for "Russian Ecological Party "Zelenye"" [https://partygreen.ru](https://partygreen.ru)
20. LDPR - number of votes for "Liberal-Democratic Party of Russia" [https://ldpr.ru](https://ldpr.ru)
21. Novye_Ludi - number of votes for "Novye Ludi" Party [https://newpeople.ru](https://newpeople.ru)
22. Edinaya_Rossiya - number of votes for "Edinaya Rossiya" Party [https://er.ru](https://er.ru)
23. Spravedlivaya_Rossiya - number of votes for "Spravedlivaya Rossiya" Party [https://spravedlivo.ru](https://spravedlivo.ru)
24. Yabloko - number votes for Yabloko Party [https://www.yabloko.ru](https://www.yabloko.ru)
25. Partiya_Rosta - number of votes for "Partiya Rosta" [https://rost.ru](https://rost.ru)
26. RPSS - number of votes for "Russian Party of Freedom and Justice" [http://rpss.ru/](http://rpss.ru/)
27. Kommunisty_Rossii - number of votes for "Communists of Russia" Party [https://komros.info](https://komros.info)
28. Grazhdanskaya_Platforma - number of votes for "Citizen Platform" Party [http://праваяпартия.рф](http://праваяпартия.рф)
29. Zelenaya_Alternativa - number of votes for "Green Alternative" Party [https://zaecology.ru](https://zaecology.ru)
30. Rodina - number of votes for "Rodina" Party [https://rodina.ru](https://rodina.ru)
31. Partiya_Pensionerov - number of votes for "Party of Pensioners" [https://pensioner.party](https://pensioner.party)
32. url - link to the page of uik inside "Elections" State System.
