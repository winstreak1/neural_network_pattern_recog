# Assignment 5: Neural Network Pattern Recognition

    Peter Mavronicolas
    Old Dominion University
    CS 580, Fall 2022
    Dr. Yaohang Li
    November 28,2022

## Task 1
### Importing
The data file named "optdigits-orig.windep.Z" was downloaded and unzipped using WinZip. This revealed the filename 
"optdigits-orig.windep". For simplicity's sake, I changed the filename to "optdigits". Next, I 
imported the data into Matlab which revealed (1) column and 59,301+ rows of data. I then copied the data from 
Matlab and pasted it into a new excel file which I named "optdigits.xlsx".

### Data Cleaning
The beginning of the file contained informational rows that were discarded though manual data cleaning. I was now 
left with 59,301 rows. In order to concatenate each set of 32 rows that depicted the number 0-9 in 0's and 1's, I
applied the following command:
```commandline
concat = strcat(DATA{1:32,1});
```
The output successfuly concatenated 32 rows (1-32) of the optdigits.xlsx spreadsheet into one column.

### Looping through the Spreadsheet
Finally, I created a for-loop after watching several YouTube videos that would iterate through the spreadsheet;
copying each iteration to a new file named "optdigitd2.xlsx". I then created a for-loop to iterate throught the spreadsheet. 
```commandline
%input data
DATA = readcell('optdigits.xlsx');
%declare variables
cell_beg = 1;
cell_end = 32;
column = 33;

%loop through spreadsheet and concatenate every 32 rows. Create column header on 33rd row.
for row = 1:size(DATA,1)
    %concatenate ever 32 rows
    concat = strcat(DATA{cell_beg: cell_end, 1});
    
    %update rows to be iterated
    cell_beg = cell_beg + 33;
    cell_end = cell_end + 33;
    column = column + 33;
    end
```

Unfortunately, after several hours of attempting to
create the new spreadsheet, I was constantly given the command line error which read the following:
```commandline
Index in position 1 exceeds array bounds. Index must not exceed 59298.
```
If time permits, I plan to re-visit this code and correct my errors.

## Task 2: Option 2
### Train
To begin, be sure to include Matlab's Neural Network during installation. An alternative which is 
used in older version of Matlab is type to the following command:
```commandline
nnprtool
```
Once the neural network pattern recognition tool is opened, I imported the Cancer data set provided
by Matlab. I left the default setting of Training Data 70%, Validation Data 15%, Test Data 15%. The
layer size was increased to 20 as demonstrated in class.

### Results
![Alt text](https://assets.digitalocean.com/articles/alligator/boo.svg "a title")


### Analysis

## Works Cited
* MATLAB. (2020, July 21). How to use source control in Matlab with GitHub. YouTube. Retrieved November 30, 2022, from https://www.youtube.com/watch?v=O7A27uMduo0 
* nanohubtechtalks. (2022, October 12). Data Cleaning with MATLAB. YouTube. Retrieved November 30, 2022, from https://www.youtube.com/watch?v=tfxh5ykuBmI 
* Alligator.io. (2020, October 12). How to add images in Markdown. DigitalOcean. Retrieved November 30, 2022, from https://www.digitalocean.com/community/tutorials/markdown-markdown-images 