# Students-Performance-Analysis-System-

 # 1.Introduction

All education institutions keep marks of their students; however, without converting these marks into totals, averages, grades, and pass/fail results, the marks alone cannot give an idea of who is doing good, who requires help and in what subjects problems arise. Calculation of the marks in a form of totals, averages, grades, and pass/fail results will give an answer to these questions. This problem is solved by Student Performance Analysis System written in Python programming language. The system takes a dataset of 18 students that are taking classes on five subjects, i.e. Python, Java, Linux, AI, and SQL in the form of Pandas Data Frame and performs all calculations using NumPy library. Grade calculation and pass/fail check are performed using reusable functions and loops. Apart from the results of each student, the system calculates class average values, min/max marks, pass percentages. Subject-wise analysis shows the easiest and the most difficult subject for the class, which can be used by teachers to determine where extra efforts are required. The best-performing students in the class are recognized and ranked.

#  1.1  Problem Statement 

Most of the times, student grades and attendance in school are recorded in spreadsheet and manually calculated. The problem in calculating totals, averages, grade and pass/fail of a student is that it takes long period of time and it is very prone to error because same formula must be repeated in case of many students and even a mistake can lead to change in results. Another problem is that in case grading criteria and pass/fail criteria are not clearly stated there may arise inconsistencies in the outcome. Furthermore, in case of manual methods it is very hard to analyse class performance pattern like highest and lowest performing students and subjects where students find difficulty to score high. Therefore, top students and weak students cannot be found on time. The solution proposed for these problems is a program which as input will take a table containing marks and attendance of students and then as output it will calculate total and average marks of each student. In addition, it will assign grade on the basis of clear criteria, it will determine whether student passed or failed based on some condition and will also conduct subject wise analysis.


# 2.	Objective 

It is common for teachers to manually input and keep track of student scores in spreadsheets. This process is time-consuming and susceptible to errors, and provides no information on how the class or individual subjects fare as a whole.
This project automates all of this with the use of Python. It:
1) Calculates the total and average marks of each individual student,
2) Grades the student based on the defined rule,
3) Determines whether a student passes or fails,
4) Determines the best, worst and average performers,
5) Analyses individual subjects, 
6) Finds the top performers.

# 3 Technologies Used in this Student Performance Analysis System

<img width="857" height="480" alt="image" src="https://github.com/user-attachments/assets/3b6f444d-ae4a-4b6f-bb4b-9d5b8b8b38d1" />

  
# 4  Dataset Description 

<img width="897" height="347" alt="image" src="https://github.com/user-attachments/assets/298f91d3-ff43-49e9-a312-11751b0e45a8" />

Department column: the original dataset has no `Department` field, but the project requires one. I added a `Department` column (Computer Science, Information Technology, AI & Data Science), assigned to students in rotation, so six students fall in each department. These values are illustrative only.

#                                  5  Analysis and Implementation 

The whole project is in one notebook, `Student performance system .ipynb`.

# Step 1 : Import Libraries

Pandas , NumPy, matplotlib, seaborn  are imported

# Step 2 : Load the Data

The CSV is read into a pandas DataFrame the pd.read_csv(), df.head(), df.tail() df.info(), df.describe(), df.isnull().sum()  there is no missing values in the dataset. 

# Step 3 : Clean and Organise the Data

1)	Attendance has the % sign removed with str.rstrip (“%”) and is converted to a float.
2)	A Department column is added using a loop.
3)	The original Column is added using a loop.
4)	The Original Total Column is renamed Source_Total  and kept only for validation.
5)	Columns are reordered into a clean layout.

# Step 4: Define the Rules

Grading Rule (based on average marks, with every subject out of 100):

<img width="807" height="302" alt="image" src="https://github.com/user-attachments/assets/08570f0c-26a5-463d-9548-8e8446204c3c" />

Pass/Fail rule: a student  passes only if marks are ≥ 40 in every subject and attendance is
≥ 75%. Otherwise the student fails. The thresholds are stored as constants (`PASS_MARK`,
`MIN_ATTENDANCE`, `GRADE_BOUNDARIES`), so they are easy to change.


# Step 5: Reusable functions

<img width="852" height="412" alt="image" src="https://github.com/user-attachments/assets/fd4e00e7-e5aa-4b08-8c3f-224aea4536bd" />

# Step 6: Student-wise results

The marks columns are converted to a NumPy matrix with `df[SUBJECTS].to_numpy()` (students × subjects).
Total, average and percentage are calculated with the functions above. A `for` loop then assigns each student's grade, pass/fail status and failed subjects. The calculated totals matched the file's `Total` column in all 18 rows.


# Step 7: Overall performance

np.argmax() and np.argmin() find the students with the highest and lowest totals. np.mean(),
np.median()  and np.std() give the class statistics.

# Step 8: Subject-wise analysis

A for loop runs through each subject, calls subject_statistics() , and collects the results into a
DataFrame. A second loop finds the topper and lowest scorer in every subject.


# Step 9 : Top performers

Students are ranked with rank() and sorted by total marks (attendance breaks ties) to get the top 5.
Another loop finds the best student in each department.

# Step 10: Department summary, charts and export
groupby().agg()  summarises each department. Matplotlib draws four charts and a marks heatmap. The final
report is saved to Student_Performance_Report.csv .

#   Data Analysis Questions and Answers 

# 1)	Which student has the highest average?

<img width="939" height="86" alt="image" src="https://github.com/user-attachments/assets/5c174d49-b5a8-4cf4-a5e5-8bd17c407755" />

# 2)	Which subject has the best average?

<img width="940" height="86" alt="image" src="https://github.com/user-attachments/assets/b166beb6-4a04-442d-ad04-2a5ff21daee9" />


# 3)	How many students passed?

<img width="958" height="78" alt="image" src="https://github.com/user-attachments/assets/322809ad-dc33-4ed2-9c75-a77d1dbdbb96" />

# 4) What is the overall class average?

<img width="930" height="73" alt="image" src="https://github.com/user-attachments/assets/d2de2fe1-bc78-4a23-8afd-2ba85b4df8c4" />


# 6. Key Features

1)  Loads and organises data with a  Pandas DataFrame
2)NumPy used for sums, means, medians, standard deviation and finding max/min positions
3) Reusable functions for totals, averages, grades, pass/fail and subject statistics
4) Loops  for grading, pass/fail checks, subject analysis and department toppers
5) Total, average and percentage  calculated for each student, with an automatic check against the source file
6) Grade assignment  from a clearly defined table
7) Pass/Fail  from a clear condition, with the exact failed subjects listed
8) Highest, lowest and average  class performance
9) Subject-wise analysis : average, median, highest, lowest, standard deviation, pass %, topper, lowest scorer
10) Top-performer ranking  and best student per department
11) Department-wise summary
12) Visualisations  and  CSV export  of the final report



# 7. Results of this Project 

<img width="915" height="884" alt="image" src="https://github.com/user-attachments/assets/6d3c30ff-d509-4add-9a9a-932659db0061" />


<img width="929" height="361" alt="image" src="https://github.com/user-attachments/assets/cfa6d1bb-73ab-4434-93d1-35099edac67f" />


<img width="1043" height="833" alt="image" src="https://github.com/user-attachments/assets/def7c89c-294d-493f-92e4-49686aebe825" />


<img width="1076" height="515" alt="image" src="https://github.com/user-attachments/assets/7765176b-8f6c-4608-84a4-5614a76de73d" />


<img width="995" height="519" alt="image" src="https://github.com/user-attachments/assets/51b7b9e9-f218-4239-b43c-1ee07a00da71" />


<img width="970" height="1016" alt="image" src="https://github.com/user-attachments/assets/3cbd8105-4164-4d77-9255-77efe9c82eea" />


<img width="713" height="600" alt="image" src="https://github.com/user-attachments/assets/5e57cca3-6665-4ffe-ba44-40977fdacea7" />


<img width="718" height="360" alt="image" src="https://github.com/user-attachments/assets/f6e4ae93-1819-4bc9-8754-dd9150bd32fe" />


<img width="769" height="289" alt="image" src="https://github.com/user-attachments/assets/22355656-98cf-446d-b0d5-11aabcba43d3" />


<img width="921" height="175" alt="image" src="https://github.com/user-attachments/assets/8944dc50-7043-4ac4-94a6-6ecd45dba2af" />


<img width="764" height="278" alt="image" src="https://github.com/user-attachments/assets/7bc1642d-3c69-4837-ab49-0d1a1bc12d3a" />


<img width="915" height="503" alt="image" src="https://github.com/user-attachments/assets/59996560-3d81-4114-84f8-97aeafec05b2" />


<img width="919" height="600" alt="image" src="https://github.com/user-attachments/assets/a1d62f29-9eb8-4987-9d72-e0bcbc1bacae" />


<img width="915" height="650" alt="image" src="https://github.com/user-attachments/assets/421d13a2-dbf0-4134-94cb-aec3215eb114" />


<img width="1064" height="541" alt="image" src="https://github.com/user-attachments/assets/456249a5-1585-40a3-bbdd-a9b6da83109b" />


<img width="900" height="912" alt="image" src="https://github.com/user-attachments/assets/b017049c-5412-4e06-8d65-c5f493536c3a" />


<img width="1006" height="216" alt="image" src="https://github.com/user-attachments/assets/edc57521-ee6f-4f7a-9197-32fa6c3fa929" />


#  8. Final Outcome  of this Project 

The project turns a raw marks sheet into a complete performance report:
1) Total, average, grade and pass/fail status were generated for all 18 students, and the calculated totals matched the source file exactly.
2) The class average is about  65.4 marks . Lal  scored the highest total (421) and Bhaskar  the lowest (266).
3) Linux  is the strongest subject (average 69.44) and  AI  the weakest (average 62.56, pass rate 77.8%), so AI may need extra attention.
4) All 8 failures were caused by scoring below 40 in at least one subject, not by attendance (the lowest attendance was 94%).
Because the logic lives in reusable functions with adjustable constants, the notebook works on a new CSV or a different grading or pass rule with almost no changes.


#  9. Challenges of this Project 

1) Attendance` was stored as text ("97%") and could not be used in calculations | Removed the % sign and converted the column to float 
2) The dataset had no `Department` column   Added one by assigning departments with a loop, and stated this assumption clearly 
3)  Grade and pass/fail rules were not given  Defined the rules explicitly and stored them as constants so they are easy to change 
4) Making sure the calculations were correct  Compared my calculated totals with the file's `Total` column (0 mismatches) 
5) Mixing vectorised and loop-based code | Used NumPy for whole-array maths and loops only where each student or subject is handled individually 


# 10   Future Scope  and Conclusion

# Future Scope 

The Student Performance Analytics System could be worked on a bit more, like adding extra stuff, so the whole way we look at student performance becomes faster and more helpful in real life. Right now it’s pretty solid, but with a few upgrades, it can feel much more useful. Honestly, something like this can turn into a bigger monitoring and decision-support tool, not just a Python setup with graphs.
1. Web-Based application: It could be turned into a web platform, so teachers and students can access the performance reports online without that back and forth, file saving and all.
2. Interactive dashboard: An interactive dashboard might be built with tools like Power BI, Tableau, or even Streamlit, to show marks, attendance, grades, also the performance trends that change over time. It would be less “static” and easier to understand.
3. Predicting performance using machine learning: Machine learning could be used to estimate how a student might do next, based on previous marks, attendance records, and other relevant factors. Not magic of course, but more of a smart guess.
4. Attendance analysis: The system could check the link between attendance and academic results, to find patterns. Like, if lower attendance leads to weaker outcomes, the tool can highlight that, early-Ish.
5. Automated report generation:  Reports for each student could be generated automatically, maybe in PDF or Excel, and also for the full class in one go, which saves time.
6. Early recognition of low-performing students: The system could flag students who might need additional academic support. This can be based on a combination of marks, attendance, and earlier performance.
7. Database integration: A database such as MySQL can be connected, so student records are stored properly, updated smoothly, and pulled when needed.
8. Real-time data updates:  Finally, the system could be improved so reports refresh automatically whenever new marks or attendance entries are added, instead of waiting for manual runs.

# Conclusion

The Student Performance Analytics System was built using Python and it’s data analysis tools, including Pandas, NumPy, Matplotlib, and Seaborn. Honestly the whole idea is to look at how students are doing academically and then show the outcomes in a more clear and not too messy way. Basically the system handles student marks and attendance, it then computes total marks, average marks, and percentages. After that it goes into grades, pass or fail signals, and even student rankings. On top of that it gives subject based and department based summaries, and it visualizes the main points with charts, plus a correlation heatmap that ties things together. Overall this project shows how Python can automate data handling, cut down on manual number crunching, and pull out useful insights from student records. It also built real, hands on skills like data cleaning, data manipulation, statistical analysis, visual storytelling, and report compilation. To wrap it up, the Student Performance Analytics System gives a solid starting base for understanding academic performance using data analysis. And with future improvements like machine learning, interactive dashboards, and database integration, it could become a more advanced platform for monitoring students closely, and supporting better academic decisions, without all the extra hassle.









































