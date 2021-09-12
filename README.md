# instructor-scheduler
Python resource for scheduling instructor resources.

## Usage
```
usage: Main.py [-h] -i INSTRUCTORS -c CLASSES [-f FILTER]
```

## Dependencies

pandas, numpy, OR tools

Install [OR tools](https://developers.google.com/optimization/install).
E.g.  
```
python -m pip install --upgrade --user ortools
```

## Input

### 
Create the CLASSES file.

Download your schedule from student admin.
Open up the .XLS file and export to TSV (tab delimited file -- use "save as" in the file menu)
![download_to_excel](https://user-images.githubusercontent.com/8617007/133003252-964d5b29-c2cf-4185-bfa3-36da4263352b.png)
Add instructors and their availability in the TSV file. Each instructor has their own column and a 1 in the row if they can fill the section. I typically do this by opening the TSV back up using excel. To facilitate this, if you run the original TSV into the program it should output a cleaned version with suffix "_filtered.tsv".

### Create the INSTRUCTORS file.

Create a TSV file with 3 columns and each line being the instructors name, minimum classes they can cover, and maximum classes they can cover.

### Filtering course names
If you only want to consider a single course (e.g. CSE 1010) then add a filter with -f, e.g., "-f 1010"

### Run the program
```
python Main.py -i data/num_labs_ta_assignment.txt -c data/class_times_withtas.txt -f 1010
```
