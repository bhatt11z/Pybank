# Pybank

Requirements:
  - Juypter Notebook.
  - Pyhton libraries: CSV, Pathlib, Statistics.

Overview:

I created a Python script to analyze the records in budget_data.csv and calculate the following:
  - Total number of months.
  - Net total amount of Profit/Losses over the entire period.
  - Average of the changes in Profit/Losses over the entire period.
  - The greatest increase in profits.
  - The greatest decrease in losses.  

Results:

- Script Summary:
   with open (budget_data, 'r') as csvfile:
    csvreader = csv.reader(csvfile, delimiter = ',')
    csvheaders = next(csvreader)
    for row in csvreader:
        total_months += 1
        total_revenue += int(row[1])
        if int(row[1]) > greatest_increase:
            great_month = (row [0])
            greatest_increase = int(row[1])
        elif int(row[1]) < greatest_decrease:
            worst_month = (row[0])
            greatest_decrease = int(row[1])
        change.append(int(row[1]))
        
for i in range(len(change)- 1):
    changes = (change[i+1] - change[i])
    monthly_change.append(changes)   

average_change = round(statistics.mean(monthly_change),2)

print(f"Total months: {total_months}")
print(f"Total profit: $ {total_revenue}")
print(f"Greatest decrease : $ {greatest_decrease}" + " " + worst_month)
print(f"Greatest increase : $ {greatest_increase}" + " " + great_month)
print(f"Average change : $ {average_change}")
 
  
- Result:
  Total months: 86
  Total profit: $ 38382578
  Greatest decrease : $ -1196225 Sep-2013
  Greatest increase : $ 1170593 Feb-2012
  Average change : $ -2315.12



