## MONGODB Statements - Zen Class Programme using Aggregate method for below Questions:   

1. Find all the topics and tasks which are thought in the month of October   
   &emsp;a. **Stage1**: *$match* - $expr, $eq, $month - to fetch the topic details completed in October   
   &emsp;b. **Stage2** : *$lookup* - joined topics and task collections   
   &emsp;c. **Stage3** : *$unwind* - converts the resultant Array to an Object for easy handling   
   &emsp;d. **Stage4** : *$project* - projected specific fields for display the final result   
2. Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020   
   &emsp;a. **Stage1**: *$match* - $gte, $lte - fetches data between the given date range   
3. Find all the company drives and students who are appeared for the placement.
   &emsp;a. **Stage1** : *$lookup* - joined users and company_drive collections   
   &emsp;b. **Stage2** : *$project* - projected specific fields for display the final result   
4. Find the number of problems solved by the user in codekata   
   &emsp;a. **Stage1** : *$lookup* - joined users and codekata collections   
   &emsp;b. **Stage2** : *$unwind* - converts the resultant Array to an Object for easy handling   
   &emsp;c. **Stage3** : *$project* - projected specific fields for display the final result   
5. Find all the mentors with who has the mentee's count more than 15
   &emsp;a. **Stage1** : *$lookup* - joined users and mentors collections   
   &emsp;b. **Stage2** : *$project* - projected specific fields for display the final result     
   &emsp;c. **Stage3** : *$group* -   grouping the students based on the primary id - mentor_id and pushed the stucdents name into an Array
   &emsp;d. **Stage4** : *$unwind* - converts the resultant Array to an Object for easy handling   
   &emsp;e. **Stage5**: *$match* - $expr, $gt, $size, $ifNull - fetches the Mentors with more than 15 mentees   
6. Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020
   &emsp;a. **Stage1** : *$lookup* - joined users and task collections   
   &emsp;b. **Stage2** : *$unwind* - converts the resultant Array to an Object for easy handling   
   &emsp;c. **Stage3** : *$lookup* - joined resultant data with attendance collections   
   &emsp;d. **Stage4** : *$unwind* - converts the resultant Array to an Object for easy handling   
   &emsp;e. **Stage5** : *$project* - projected specific fields for display the final result     
   &emsp;f. **Stage6**: *$match* - $lte - fetches the absentees and students who have not completed the Task within the given date range.       

***Author : Tharani K***
