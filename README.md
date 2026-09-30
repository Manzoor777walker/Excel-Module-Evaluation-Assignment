# Excel-Module-Evaluation-Assignment
## By exploring  relationships between various health metrics, identifying trends, and visualizing key patterns, we  aim to deliver actionable insights to healthcare stakeholders for informed decision-making  through rigorous data cleaning, transformation, exploration, and analysis. 
# *DATA CLEANING*
            *Using find and relace function to replace "?" to blank cell on both “MedicalExaminations” Table and "Hospitalization Details" Table.
            *Fill in the missing values of ‘month’ with Sep also using find and replace method and also in the case of ‘year’  using conditional formating and 
                 highlight cell and replace year with its average rounded to the  nearest integer, in the data set which is 1983.
            * Replace the value by using filter method and count function to find frequently occurring values in the ‘smoker’, 'Hospital tier' and 'City
tier' columns, and fill in the missing values accordingly in Medical examination sheet,Hospital detail sheet.
             *In 'State ID' of Hospital record details using filter method to identify missing values and change it into 'Unknown' data.
# *Data Transformation*
             *Split the ‘names’ column in the “Customer Names” Table into 3 meaningful columns:‘Title’, ‘First Name’, and ‘Last Name’ by using Text to Column Function and rearrange the column in the mentioned order.
             *Convert the "NumberOfMajorSurgeries" column in the “Medical Examinations” Table to numerical data by replacing non-numeric characters 
with meaningful numerical values.
        # Change the data type  of "NumberOfMajorSurgeries" column  into Number Format and insert a new column use find and replace method  to fill the column.
              *Check for inconsistencies in the 'Heart Issues' and 'smoker' columns and propose corrective actions if necessary.
                                            #Change data set into tables
                                            # create a two new table['G'] and['L'] using proper and trim function[[Refer Medical Examination sheet]
                                            #Formula Used as:[=TRIM(PROPER([@[Heart Issues]]))]             
            * Create a new column named “Weight Status” that categorizes BMI into different categories [Refer Medical Examination Sheet -{Table 'C'}
                               using Formula: [=IFS(C2>=30,"Obesity",C2>=25,"Overweight",C2>=18.5,"Normal Weight",C2<=18.5,"Underweight")]
            * Create a new column named “Diabetes Status” and fill it as per the information
                        #using formula:[=IFS(E2>=6.5,"Diabetes",E2>=5.7,"Prediabetes ",E2<5.7,"Normal")] Refere Medical Examination sheet {()Table'D'}  
            *Merge ‘year’, ‘month’ and ‘date’ columns in the “Hospitalization Details” Table into one column named ‘Date of Birth’ and format it in ‘DD-MMM-YYYY’ custom format
                         #Formula used :[=TEXTJOIN(" ",TRUE,E1,"-",D1,"-",C1)] [Refer Hospital Detail Sheet()-{Table-"D","E","F"}
            *Calculate the ‘Age’ of each customer based on their ‘Date of Birth’ and the date of collection of the dataset, which is 8thJune 2023. 
                                # Create a  Column named as "Age" and covert the data type to general.
                                #Formula Used:[DATEDIF(B2,"8June 2023","Y")][Refer Hospital Detail Sheet()-{Table-"C"}
            *Format ‘charges’ column as currency ()-  [Refer Hospital Detail Sheet()-{Table-"H"}
  # *Data Exploration, Analysis & Visualization:*
             *Create a new sheet named “Healthcare", combine all three tables into one, using Customer ID as the common column, utilizing VLOOKUP.   Retain the following necessary columns: Customer ID, First Name, BMI, HBA1C, Heart Issues, Any Transplants, Cancer history, NumberOfMajorSurgeries, smoker, Weight Status, Diabetes Status, Date of Birth, charges, Hospital tier, City tier, State ID, Age.
          #sample format of formula used :[=VLOOKUP(A2,'Modified CD Sheet'!$A$2:$E$2336,4,0)]
          #Refer "Health Care sheet"
  # *Create pivot tables for doing  the following analysis, then visualize through charts*:
                    •Analysis using Pie/Donut Chart() Refer "Pivot Table Sheet"
                    •Analysis using Column/Bar Chart()Refer "Pivot Table Sheet"
                    •Analysis using Line/Scatter Plot:()Refer "Pivot Table Sheet"


# # *Create pivot tables for doing  the following analysis, then visualize through charts* and *Dashboard Creation*

                      #Build an interactive dashboard that consolidates all key insights using the above visualizations. Ensure visual clarity and ease of interpretation for all chart types. 
                      #Add slicers for the fields “Weight Status” and “Diabetes Status” to enable filtering across all visualizations, supporting comparison of health outcomes and charges based on body weight and diabetes condition
# steps:
## Analysis using Pie/Donut Chart
Chart 1: PIE CHART
### Distribution of Cancer History Among Smokers and Non-Smokers
1. Pivot Table Setup
	             •Rows: Smoker ,
               •Columns: Cancer History 
               •Values: Count of Customer ID
Chart Creation & Settings
          	•Click the Pivot Table insert Pie Chart or Donut Chart.
            •Data Labels: Right-click data labels ,Format Data Labels ,Check Percentage and uncheck Value. Set position to Outside End.
Chart 2:DONUT CHART 
### Major Surgeries & Average HbA1c by Transplant History
1. Pivot Table Setup
	•Rows:Any Transplants 
            •Values:Number of Major Surgeries ,HbA1C
                                      *Number of Major Surgeries:Set to Sum  
                                      *HbA1C :Set Summarize Values By to Average
 Chart Creation 
               •Create a Donut Chart specifically for Sum/Count of Major Surgeries by Transplant History.
               • Legend: Any Transplants 
               •Data Labels: Display percentages or total count clearly outside the ring.
               •For HbA1c, format the label as a decimal number (e.g., 6.5).For Surgeries, format the label as a whole integer count or percentage share.
   ## Analysis using Column/Bar Chart
              Chart 3:BAR CHART
 ### Healthcare Charges by Weight Status & Diabetes Status
1. Pivot Table Setup
	 •Rows: Weight Status 
                •Columns: Diabetes Status 
                •Values: Healthcare Charges
                •Right-click the value field , Summarize Values By , select Average
                •Number Formatting: Right-click any number in the table,Number Format,select Currency ($) (Ensure it is not set to Percentage %).
 Chart Creation & Formatting
          • Click inside the Pivot Table and Insert select Clustered Column Chart 
          •Hide Field Buttons: Right-click any gray button on the chart , select Hide All Field Buttons on Chart.
          •Format Vertical Axis: Right-click the vertical (Y) axis,Format Axis ,under Number, set Category to Currency.
 Chart 4:COLUMNCHART 
   ### Average Charges by Hospital Tier Across States
1. Pivot Table Setup
	•Rows: State ID
               •Columns: Hospital Tier 
               •Values: Healthcare Charges
               •Right-click the value field , Summarize Value,select Average.
               •Number Formatting: Right-click any number in the table,Number Format,select Currency ($).
    Chart Creation & Formatting
               •Click inside the Pivot Table and Insert  select Clustered Bar Chart or Clustered Column Chart.
               •Hide Field Buttons: Right-click any gray button on the chart, select Hide All Field Buttons on Chart.
                •Format Axis:Ensure the axis displaying charges is set to Currency ($). 
    ## Analysis using Line/Scatter Plot: 
Chart 5: Line Chart
### Correlation Between Age and Both BMI and HbA1C
1. Pivot Table Setup
	•Rows: Age 
               •Values:BMI:  Right-click , Summarize Values By ,select Average
                            HbA1C :Right-click  Summarize Values By,select Average.
Chart Creation & Formatting
                       •Click inside the Pivot Table and Insert  Line Chart with Markers 
                        •Secondary Axis : Since BMI ranges around 20–40 and HbA1c ranges around 4–10, putting them on one axis makes HbA1c look flat.
                                      Right-click the HbA1C line, Format Data Series.
                                      Under Series Options, select Secondary Axis.
                                      Clean Up: Right-click any gray button on the chart , select Hide All Field Buttons on Chart.
Chart 6:Line Chart 2 
### Relationship Between Age and Healthcare Charges
1. Pivot Table Setup
              • Rows: Age 
               •Values: Healthcare Charges:Right-click the value field , Summarize Values By , select Average.
               Number Formatting: Right-click any number in the table , Number Format, select Currency ($) with 0 decimal places.
Chart Creation & Formatt
                       •Click inside the Pivot Table and Insert  Line Chart  with Straight Lines/Markers.
                        •Format Vertical Axis: Right-click the Y-axis , Format Axis ,ensure Currency ($) format is applied.
                        •Hide Field Buttons: Right-click any gray button on the chart , select Hide All Field Buttons on Chart.
# Creating an Interactive Dash board
                            •making a duplicate copy of Charts Created in Pivot sheet and using ctrl+x functon to move on Dashboard sheet.
                            •Assign Each chart on the dashboard sheet for  making interactive sheet
                            •Add a slicer for connecting all these six chart and make interactive.
                            •Make necessary editing in Slicer Setting.
                            •Refer "Dashboardsheet".
                       

      







                         
