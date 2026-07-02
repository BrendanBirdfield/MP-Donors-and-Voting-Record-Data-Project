# MP-Donors-and-Voting-Record-Data-Project
Power BI Report allowing searching and comparison of UK MPs voting Record and Donations. 
data gathered via Webscraping and CSV downloads.

650 mp voting records were scraped using Selenium. A list of MPs with a link to their voting record was downloaded as a csv from https://www.theyworkforyou.com/mps/
This list was then processed using python to gather url's pointing to each MPs voting record and selenium was used to retrieve the html code containing the list of MPs voting record and append to a python list.
This data was then processed using pandas and python to clean text format of voting records. Lists of MPs votes were split into seperate rows for each individual vote. Vote descriptions were reformated for consistency and and voting sentiment scores were reformatted from text to integer data types to allow for easy comparison and quantification for example. Voting sentiment of 'Voted Generally for' was converted to the number 8. This allowed for quantifying and plotting different votes against each other.    

MPs donations were obtained from the official uk parliament website: https://members.parliament.uk/members/commons/interests/publications.
This was then processed in python using pandas text processing, to remove white space and replace characters to keep categories consistent. Missing values were filled with reasonable replacement values such as replacing empty donation amounts with 0 in order to keep data thus retaining usefulness of all rows. 
This process is documented in the MPDonorCorrelation.ipynb file: https://github.com/BrendanBirdfield/MP-Donors-and-Voting-Record-Data-Project/blob/main/MPDonorCorrelation.ipynb

Once processed, this data was then exported as a csv and imported into power BI. 
A star schema data model was used to split individual votes into a distinct fact table with relationships linked to two dimension tables representing information on individual MPs such as their political party and a dimension table for each donation made to every MP.
<img width="1915" height="1032" alt="Image" src="https://github.com/user-attachments/assets/c2ec758c-f9c1-4a38-82a5-ebe90c389a26" />
Two main pages were created. 
The first allows comparison of voting records of political parties using slicers to select political parties or individual MP's. The second slicer is for choosing a specific votes to compare.
The neutrality constant line indicates a 50/50 split of votes for and against. Anything above the line represents an increasing for/pro sentiment ie. voting generally for or mostly for. 
Anything below the line indicates a voting sentiment against the selected vote. 
Below compares the average voting sentiment of all parties on voting for a stricter asylum system. As expected the Reform and Consevative parties voted strongly in favour. 
<img width="1919" height="1031" alt="Image" src="https://github.com/user-attachments/assets/7f7e940a-522c-4132-92c8-30253c681a97" />
This same page allows comparing individual MP's on specific votes:
<img width="1919" height="1029" alt="Image" src="https://github.com/user-attachments/assets/58144002-605c-459d-898d-c943c7361dca" />

A second page allows for comparison of donations by amounts and donation categories between MP's and politcal parties.
A tooltips pop up appears when scrolling over each category to show summary details of each individual donation.
<img width="1919" height="1079" alt="Image" src="https://github.com/user-attachments/assets/6ae981fc-afc1-4efd-8dce-f644ad939570" />
