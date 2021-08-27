# Data Stories for Sprint 0

## Dev setup
- Python (^3.6)
- A conda environment with jupyter lab, pandas, numpy
- Java JDK
- Download the [Synthea Jar file](https://github.com/synthetichealth/synthea/wiki/Basic-Setup-and-Running#installation)
- Clone the Synthea repo
- Make the following directory structure in your `projects` folder

```
synthea/
├── synthea/  # the cloned github repo
│   ├── src/
│   │   └── main/
│   │       └── resources/
│   │           └── synthea.properties
├── synthea.jar # the jar file you downloaded
├── synthea-dev.properties # copy this file from the above directory
└── output/ # the output directory you're going to spit out your data to
```

- Once you copy the `properties` file, change the `export-csv` options to true and the `export-fhir` options to false.

# Opioid Addiction

``` bash
java -jar synthea.jar "New York" -c "./synthea-dev.properties" --exporter.baseDirectory "/users/lpanda/Documents/output/" -a 18-100 -p 10 -m "Opioid*" --exporter.years_of_history 7
```

Output should look like:

``` bash
Loading module modules/opioid_addiction.json
Running with options:
Population: 1000
Seed: 1629171503437
Provider Seed:1629171503437
Reference Time: 1629171503437
Location: New York
Min Age: 18
Max Age: 110
Modules: Opioid Addiction Module
       > [1 loaded]
Records: total=1113, alive=1000, dead=113
```
