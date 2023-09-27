# Web Scraping a Property Listing Website
![](intro.jpg)
## Introduction
This project leverages Python's versatility in performing web scraping and data cleaning operations before analysis and visualization was completed in Power BI. Real-time data from [Property24](https://www.property24.com.ng/1-bedroom-properties-to-rent-in-lagos-p37?), a local property listings website was scrapped. The goal of the project was to make a single-page dashboard that helps property renters find their dream homes.
## Skills demonstrated
The following Python skills were incorporated into this project.
- Importing Python libraries.
- Web page retrieval.
- HTML parsing.
- Handling dynamic content.
- Data extraction and storage.
- Data cleaning.

The following Power BI skills were also incorporated into this project.
- Data transformation.
- Knowledge of DAX functions.
- Drill through page
- Data analysis and visualization.
## Data sourcing
The data was obtained via scrapping of rental properties on [Property24](https://www.property24.com.ng/1-bedroom-properties-to-rent-in-lagos-p37?), a local property listing website. On the website, the location was set to 'Lagos', and the number of beds was set to '1+' in order to achieve the project's aim. Applying these filters on the website reduced results to just 181 properties. This was done to avoid overloading the website with requests, ensuring a smoother and more considerate scraping process that respects the website's server capacity and performance.

A well-commented [Python script](https://github.com/emmywritescode/Web-Scraping-a-Property-Listing-Website/blob/main/Web%20Scraping%20a%20Property%20Listing%20Website.ipynb) was crafted within Jupyter Notebook, employing essential libraries like BeautifulSoup, Selenium's WebDriver, and Pandas. A base URL  was initiated which iterated through web pages, gathering desired data into predefined lists. The loop ceased once pages no longer met the scraping criteria. The dataset comprises 191 rows and 5 columns, following the data extraction process. Finally, the data was stored in a data frame and exported as a CSV file.
## Data cleaning and Data transformation
The data cleaning process began with the removal of the leading and trailing spaces within the dataset. Records of some commercial properties were also obtained in the scrapping process and they were dropped. A separate column 'Bedroom' was created to store the number of bedrooms in each property. To clean the Price column, a function was defined to take care of the '₦' prefix and the spaces while some price values were adjusted properly to align with the data consistency. A function was also defined to replace null values in the Location column  with information from the Name column. The Location column was then adjusted to retain only the city where the properties are located. Lastly, duplicate values were dropped. Overall this process reduced the records to a tidy 175. The script can be read [here](https://github.com/emmywritescode/Web-Scraping-a-Property-Listing-Website/blob/main/Cleaning%20the%20Dataset.ipynb).

The data was further transformed in the Power Query Editor on Power BI. The 'Period' column was renamed to 'Rent Period', 'Price' column was renamed to 'Rent', and the values were formatted to the appropriate currency. A conditional column called 'Condition' was created, which classifies properties into 'Newly-built' and 'Existing' based on the presence of words like 'New' and 'Newly' in the 'Detail' column. Another conditional column called 'Class' was created using DAX, which groups properties into 'Economy,' 'Standard,' and 'Luxury' based on the corresponding Rent Period and Rent.
## Analysis and Visualization
Analysis revealed the following:
- There are 175 properties of which is Existing and only Newly-built.
- of the properties give potential home dwellers the opportunity to pay rent on a 'Per Year' basis and '' allowed rent to be paid on a 'Per Month' basis.
- Most of the properties can be classed as 'Standard'
![]()
The interactive dashboard can be accessed [here]().
## Conclusion
The dashboard provides a comprehensive overview of rental properties listed by Estate Hub 24. The use of interactive filters allows potential home renters to zero down on their preferred choices based on the available listings. A drill-through page also provides further details of each property including the exact rent based on the rent period. Overall, the property listing firm has made it easy for everyone to discover their dream home without any hassle.






