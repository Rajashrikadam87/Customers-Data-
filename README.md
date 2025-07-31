# Customers Data - Cleaning Sales Data and Dashboard Project

## Project Overview
This project showcases the complete process of cleaning customer sales data and building an interactive Excel dashboard. It includes raw data, step-by-step cleaning (with formulas), and a dashboard that provides insights into purchase amounts and customer counts by country, filtered by membership levels (Gold, Silver, Platinum).

## Tools Used
- Microsoft Excel
- Power Query
- Pivot Tables
- Pivot Charts
- Slicers
- Excel Formulas (for data cleaning)

## Project Structure
- Raw_Data.xlsx: Original uncleaned customer sales data
- Data_Cleaning_Steps.xlsx: Contains cleaning steps with applied formulas
- Cleaned_Data.xlsx: Final cleaned dataset ready for analysis
- Sales_Dashboard.xlsx: Interactive dashboard with filters and visuals
- README.md: Documentation file (this file)

## Data Cleaning Steps
- Removed rows with missing or null values
- Fill rows with average value
- Used formulas to fix text formatting and standardize values (e.g., PROPER(), TRIM())
- Standardized country names (e.g., India, USA, UK)
- Cleaned inconsistent membership labels (e.g., gold → Gold)
- Converted Purchase Amount to numeric
- Used Power Query to transform and clean the Date of Joining
- Removed duplicate and empty Customer IDs
- Verified and cleaned email and phone number formats

   ## Key Excel Formulas Used

Below are the main formulas used during data cleaning in Excel:

- *Age Cleaning*  
  Replace 0 or negative values with column average:  
  =IF(C2<=0, AVERAGE(C:C), C2)

- *Gender Standardization*  
  Map common variations to 'Male' or 'Female':  
  =IF(OR(LOWER(E3)="m", LOWER(E3)="male"), "Male", IF(OR(LOWER(E3)="f", LOWER(E3)="female"), "Female", IF(E3="", "Other", E3)))

- *Email Cleanup*  
  Replace (at) with @ and handle blanks:  
  =SUBSTITUTE(H2, "(at)", "@")  
  =IF(I2="", "Follow up needed", I2)

- *Phone Number Validation*  
  Handle blanks and ensure proper length:  
  =IF(K2="", "Number is needed", IF(LEN(K2)>10, "Invalid", VALUE(K2)))

- *Country Cleanup*  
  Standardize spelling:  
  =IF(OR(M2="India", M2="ind"), "INDIA", IF(M2="Usa", "USA", IF(M2="", "", "UK")))

- *Purchase Amount Cleaning*  
  Fill missing or NaN values and convert to integer:  
  =IF(OR(O2="", O2="NaN"), AVERAGE(O:O), O2)  
  =INT(...)

- *Membership Standardization*  
  Capitalize first letter:  
  =PROPER(R2)

## Dashboard Features
- Purchase Amount by Country (Bar Chart)
- Customer Count by Country (Column Chart)
- Slicer for Membership Type: Gold, Silver, Platinum
- Clean layout with quick filters for dynamic insights

## Purpose and Learning Outcome
This project helped me practice the end-to-end data workflow using Excel. I learned how to clean messy raw data using formulas and Power Query, then create a structured dashboard with Pivot Tables and interactive slicers to gain business insights.
