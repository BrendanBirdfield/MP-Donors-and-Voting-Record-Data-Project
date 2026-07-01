# MP-Donors-and-Voting-Record-Data-Project
Power BI Report allowing searching and comparison of UK MP's voting Record and Donations. 
data gathered via Webscraping and CSV downloads

650 mp voting records were scraped using Selenium. A list of MP's with a link to their voting record was downloaded as a csv from https://www.theyworkforyou.com/mps/
This list was then processed using python to gather url's pointing to each mp's voting record and selenium was used to retrieve the html code containing the list of mps voting record and append to a python list.
This data was then processed using pandas and python to clean text format of voting records.  Lists of mps votes were split into seperate rows for each individual vote. Vote descriptions were reformated for consitency and and voting sentiment scores were reformatted from text to integer data types to allow for easy comparison and quantification. 

MP's donations were obtained from the official uk parliament website: https://members.parliament.uk/members/commons/interests/publications.
This was then processed in python using pandas text processing was used to remove white space and replace characters to keep categories consitent. Missing values were filled with reasonable replacement values such as replacing empty donation amounts with 0 in order to keep data and retain usefulness of all rows. 

Once processed, this data was then exported as a csv and imported into power BI. Two main pages were created. The first allows searching for specific mps or political parties and specific vote categroies using a slicers.
![Alt text](/MP-Donors-and-Voting-Record-Data-Project/Party Voting.png?raw=true)

These slicers connect to a bar graph of sentiment allowing comparison of voting sentiment between indiviual mp's and or political parties.
A second page allows for comparison of donations by amounts and categories between mps and politcal parties. 
