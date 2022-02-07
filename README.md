# Task description

For this project, I was given a dataset of Santander Cycles:
https://console.cloud.google.com/marketplace/product/greater-london-authority/london-bicycles

I was supposed to analyze the dataset and find 2 unordered pairs of stations for each month of 2016 with **the biggest decrease in average travel duration between them on the weekends as opposed to the weekdays.**


## Requirements

1. We only consider data from 2016
2. duration field is not empty
3. travel duration is **at least 10 minutes**
4. Both stations have non-empty name fields
5. Both renting and returning the bikes happened **on the same day**
6. Start and end station are not the same
7. We only consider pairs with at least 100 travels recorded in a given month


## Desired output

Output should contain at least 24 lines (if there are any ties) or exactly 24 lines (no ties). Each line must contain:
1. month number
2. name of one station
3. name of another station
4. time decrease value


# Solution description

For this task I used PySpark, therefore my whole solution is contained in the **attached Jupyter Notebook**. Apache Spark allows us to cache query results at any chosen point, therefore I cached results at a couple stages.


# End result

The result (24 lines) I received looks as follows:

|month|station_A_name                                |station_B_name                                   |ratio             |
|-----|----------------------------------------------|-------------------------------------------------|------------------|
|1    |Aquatic Centre, Queen Elizabeth Olympic Park  |Lee Valley VeloPark, Queen Elizabeth Olympic Park|1.268274812602153 |
|1    |Eccleston Place, Victoria                     |Eastbourne Mews, Paddington                      |1.1965811965811965|
|2    |Albert Gate, Hyde Park                        |Queen's Gate, Kensington Gardens                 |1.7529734183563805|
|2    |Finsbury Circus, Liverpool Street             |Waterloo Station 1, Waterloo                     |1.5393258426966292|
|3    |Crosswall, Tower                              |Waterloo Station 1, Waterloo                     |1.5388026607538803|
|3    |Hyde Park Corner, Hyde Park                   |Speakers' Corner 1, Hyde Park                    |1.341545052885259 |
|4    |Belgrove Street , King's Cross                |Northumberland Avenue, Strand                    |1.2959435626102294|
|4    |Serpentine Car Park, Hyde Park                |Black Lion Gate, Kensington Gardens              |1.2957027540360875|
|5    |Hyde Park Corner, Hyde Park                   |Storey's Gate, Westminster                       |2.14872901119403  |
|5    |East Village, Queen Elizabeth Olympic Park    |Aquatic Centre, Queen Elizabeth Olympic Park     |1.549878640776699 |
|6    |Park Road (Baker Street), The Regent's Park   |London Zoo,  The Regent's Park                   |1.7102302130616713|
|6    |Triangle Car Park, Hyde Park                  |Green Park Station, Mayfair                      |1.4917159763313608|
|7    |Green Street, Mayfair                         |Triangle Car Park, Hyde Park                     |1.8268727684095165|
|7    |East Village, Queen Elizabeth Olympic Park    |Podium, Queen Elizabeth Olympic Park             |1.6175931748270764|
|8    |Queen's Circus, Battersea Park                |Sopwith Way, Battersea Park                      |1.6915306655986828|
|8    |Wellington Arch, Hyde Park                    |Palace Gate, Kensington Gardens                  |1.5003335557038027|
|9    |Wellington Arch, Hyde Park                    |Queen's Gate, Kensington Gardens                 |1.7867634500426985|
|9    |Copper Box Arena, Queen Elizabeth Olympic Park|Podium, Queen Elizabeth Olympic Park             |1.7309442761131684|
|10   |Triangle Car Park, Hyde Park                  |Queen's Gate, Kensington Gardens                 |1.5473633558400293|
|10   |Finsbury Circus, Liverpool Street             |Waterloo Station 3, Waterloo                     |1.4538695505238257|
|11   |Black Lion Gate, Kensington Gardens           |Queen's Gate, Kensington Gardens                 |1.5203061782394751|
|11   |Belgrove Street , King's Cross                |Museum of London, Barbican                       |1.3537190082644628|
|12   |Finsbury Circus, Liverpool Street             |Waterloo Station 3, Waterloo                     |1.2488947833775421|
|12   |Holborn Circus, Holborn                       |Waterloo Station 1, Waterloo                     |1.248             |