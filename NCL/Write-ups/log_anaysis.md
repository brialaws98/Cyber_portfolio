# Challenge #1
***Name***: MCC
* Downloaded a MCC.csv log to analyze
* A Bank needs some questions answered related to transactions
### Commands {diagnosis of command}
1.  ```cat mcc.csv | grep "3795"|wc -l```<br>
      {Need to transactions for the Paris Las Vegas Hotel}
2. ```cat mcc.csv | grep "5311"```<br>
      {Need to find the only mercant in the Department Store Category}
3. ```cat mcc.csv | awk -F',' '{print $3}' | sort | uniq -c | sort -nr | head```<br>
   {
   * ```awk```(A text processing tool)
    * ```-F```(Field separator: tells you how to split the fields)
    * ```sort```(Group identical items together)
    * ```uniq -c```(Count how many times and item appears)
    * ```sort -nr```(sort items by numeric highest value)
      }
4. ```cat mcc.csv | grep "8011"```<br>
      {I Added the amount spent from mcc 8011}
5. ```cat mcc.csv | awk -F ',' '$4 > 50 {print $4}' | wc -l```<br>
      {This ask if money spent on line $4 is greater than 50 dollars}
### Solutions
1. "Paris Las Vegas Hotel" (MCC:3795) =  ```4```
2. "Department Store Category" (MCC:5311} = ```Macy's```
3. Which MCC appeared in the log the most?: ```3023 #Appears 5 times in the log```
4. The total amount spent at Doctors or Physicians(8011)? : ```198.26```
5. The total number of transactions that were above $50? : ```504```
