Download Link: https://assignmentchef.com/product/solved-dbs501-assignment1
<br>
<ol>

 <li>Write the PL/SQL block that will as input accept the two letter Country Code (check table COUNTRIES for valid values) and then it will find all locations (Cities) with empty Province information. Then it will modify this blank value to a string of same symbols, with its length determined by the length of the Street Address string.</li>

</ol>

If the city’s first letter is A, B, E or F then the string will contain only * symbol, if its first letter  is C,D, G or H then it will be <strong>&amp;</strong> symbol, otherwise it will be <strong># </strong>symbol.

Show also the modified row from Locations table and then Undo your change.

You need also to code for following cases: there is MORE THAN ONE City with empty province and also if the  Country Code does NOT have any Cities in the Locations table.

<u>Here are the possible scenarios:</u>




SQL&gt; @q1;

Enter value for country: <strong>JP</strong>

City Hiroshima has modified its province to &amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;




PL/SQL procedure successfully completed.




LOCATION_ID STREET_ADDRESS                           POSTAL_CODE

———– —————————————- ————

CITY                           STATE_PROVINCE            CO

—————————— ————————- —

1300 9450 Kamiya-cho                          6823

Hiroshima                      &amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;&amp;           JP







Rollback complete.




SQL&gt; @q1;

Enter value for country: <strong>UK</strong>

City London has modified its province to ##############




LOCATION_ID STREET_ADDRESS                           POSTAL_CODE

———– —————————————- ————

CITY                           STATE_PROVINCE            CO

—————————— ————————- —

2400 8204 Arthur St

London                         ##############            UK







Rollback complete.




SQL&gt; @q1;

Enter value for country: <strong>IT</strong>

This country has MORE THAN ONE City without province listed.




no rows selected




Rollback complete.




SQL&gt; @q1;

Enter value for country: <strong>RS</strong>

This country has NO cities listed.




no rows selected




<ol start="2">

 <li>Firstly, modify your table COUNTRIES by adding a new column called FLAG of fixed character length (7 characters).</li>

</ol>

Write the PL/SQL block that will as input accept Region Id (check table REGIONS for valid values) and then it will find all Countries with empty Location information (without City listed in that country). Then it will modify blank value in the column Flag for all such countries to become <strong>EMPTY_n</strong>  (where <strong>n</strong> is <strong>their</strong> Region Id).

Next, it will display message about that country with NO city listed and also will count how many modifications were made in total.

Show also all modified rows from Countries table sorted by Region Id and then by country name and finally Undo your change.

You need also to code for following cases: there is MORE THAN ONE Country with empty Location in the provided Region and also if the  provided Region does NOT exist.

<u>Here are the possible scenarios:</u>

SQL&gt; @q2;

Enter value for region: <strong>5</strong>

This region ID does NOT exist: 5

no rows selected

Rollback complete.

SQL&gt; @q2;

Enter value for region:<strong> 1</strong>

This region ID has MORE THAN ONE country without cities listed: 1

no rows selected

Rollback complete.

SQL&gt; @q2;

Enter value for region: <strong>2</strong>

In the region 2 there is ONE country Argentina with NO city.

Number of countries with NO cities listed is: 11

CO COUNTRY_NAME                              REGION_ID FLAG

— —————————————- ———- ——-

BE Belgium                                           1 Empty_1

DK Denmark                                           1 Empty_1

FR France                                            1 Empty_1

AR Argentina                                         2 Empty_2

HK HongKong                                          3 Empty_3

ZW Zimbabwe                                          4 Empty_4

IL Israel                                            4 Empty_4

KW Kuwait                                            4 Empty_4

NG Nigeria                                           4 Empty_4

ZM Zambia                                            4 Empty_4

EG Egypt                                             4 Empty_4

11 rows selected.

Rollback complete.




<ol start="3">

 <li>Re-write the PL/SQL block from Question 2 so that will as input accept Region Id (check table REGIONS for valid values) and then it will find all Countries with empty Location information (without City listed in that country). Then it will modify blank value in the column Flag for all such countries to become <strong>EMPTY_n</strong> (where <strong>n</strong> is <strong>their</strong> Region Id) .</li>

</ol>

Next, it will populate INDEX TABLE with all country names (without cities) in the alphabetical order, so that their key values increase by 10 (starting from 10). Also, display all their elements, count total number of elements in the INDEX TABLE and finally display SECOND  and BEFORE THE LAST element in the table (without using literal key value).

Then, it will display message about all countries with NO city listed for the provided Region Id in the alphabetical order including their total count.

Show also all modified rows from Countries table sorted by Region Id and then by country name and finally Undo your change.

You need also to code for the case: the  provided Region does NOT exist.

<u>Hint:</u>  Use Cursor For Loops where necessary and do NOT use Exception handler.

<u>Here are the possible scenarios:</u>




SQL&gt; @q3;

Enter value for region: <strong>5</strong>

This region ID does NOT exist: 5




no rows selected




Rollback complete.




SQL&gt; @q3;

Enter value for region: <strong>1</strong>

Index Table Key: 10 has a value of Argentina

Index Table Key: 20 has a value of Belgium

Index Table Key: 30 has a value of Denmark

Index Table Key: 40 has a value of Egypt

Index Table Key: 50 has a value of France

Index Table Key: 60 has a value of HongKong

Index Table Key: 70 has a value of Israel

Index Table Key: 80 has a value of Kuwait

Index Table Key: 90 has a value of Nigeria

Index Table Key: 100 has a value of Zambia

Index Table Key: 110 has a value of Zimbabwe

======================================================================

Total number of elements in the Index Table or Number of countries with NO cities listed is: 11

Second element (Country) in the Index Table is: Belgium

Before the last element (Country) in the Index Table is: Zambia

======================================================================

In the region 1 there is country Belgium with NO city.

In the region 1 there is country Denmark with NO city.

In the region 1 there is country France with NO city.

======================================================================

Total Number of countries with NO cities listed in the Region 1 is: 3




CO COUNTRY_NAME                              REGION_ID FLAG

— —————————————- ———- ——-

BE Belgium                                           1 Empty_1

DK Denmark                                           1 Empty_1

FR France                                            1 Empty_1

AR Argentina                                         2 Empty_2

HK HongKong                                          3 Empty_3

EG Egypt                                             4 Empty_4

IL Israel                                            4 Empty_4

KW Kuwait                                            4 Empty_4

NG Nigeria                                           4 Empty_4

ZM Zambia                                            4 Empty_4

ZW Zimbabwe                                          4 Empty_4




11 rows selected.




Rollback complete.




SQL&gt; @q3;

Enter value for region: <strong>2</strong>

Index Table Key: 10 has a value of Argentina

Index Table Key: 20 has a value of Belgium

Index Table Key: 30 has a value of Denmark

Index Table Key: 40 has a value of Egypt

Index Table Key: 50 has a value of France

Index Table Key: 60 has a value of HongKong

Index Table Key: 70 has a value of Israel

Index Table Key: 80 has a value of Kuwait

Index Table Key: 90 has a value of Nigeria

Index Table Key: 100 has a value of Zambia

Index Table Key: 110 has a value of Zimbabwe

======================================================================

Total number of elements in the Index Table or Number of countries with NO cities listed is: 11

Second element (Country) in the Index Table is: Belgium

Before the last element (Country) in the Index Table is: Zambia

======================================================================

In the region 2 there is country Argentina with NO city.

======================================================================

Total Number of countries with NO cities listed in the Region 2 is: 1







CO COUNTRY_NAME                              REGION_ID FLAG

— —————————————- ———- ——-

BE Belgium                                           1 Empty_1

DK Denmark                                           1 Empty_1

FR France                                            1 Empty_1

AR Argentina                                         2 Empty_2

HK HongKong                                          3 Empty_3

EG Egypt                                             4 Empty_4

IL Israel                                            4 Empty_4

KW Kuwait                                            4 Empty_4

NG Nigeria                                           4 Empty_4

ZM Zambia                                            4 Empty_4

ZW Zimbabwe                                          4 Empty_4




11 rows selected.

Rollback complete.

<ol start="4">

 <li>Write the PL/SQL block that will as input accept two strings:</li>

</ol>

<ul>

 <li>Any piece of course description in UPPER case</li>

 <li>Beginning of Instructor’s last name in UPPER CASE</li>

</ul>




Then, it will find for this input match the following items: Course Number, Course Description, Section Id, Instructor’s Surname and Course Section Number and next it will figure out about the current enrollment for that Section Id. Finally, it will provide the total number of enrolled students through all Sections found.

You need also to code for the case: provided two strings do NOT match and there is NO data.




<u>Hint:</u>  Avoid CPU consuming and performance problematic Multiple Tables Join with Grouping. You should use Nested Cursor For Loops instead, where the Inner Loop will have a parameter and will execute only once. Also, do NOT use Exception handler.

<u>Here are the possible scenarios:</u>

SQL&gt; @q4;

Enter the piece of the course description in UPPER case:<strong>DATA</strong>

Enter the beginning of Instructor last name in UPPER CASE:<strong>W</strong>

There is NO data for this input match between the course description piece and the surname start of Instructor. Try again!

SQL&gt; @q4;

Enter the piece of the course description in UPPER case:<strong>INTRO</strong>

Enter the beginning of Instructor last name in UPPER CASE:<strong>W</strong>

Course No: 120 Intro to Java Programming with Section Id: 149  is taught by Wojick in the Course Section: 4

This Section Id has an enrollment of: 1

*********************************************************************

Course No: 25 Intro to Programming with Section Id: 88  is taught by Wojick in the Course Section: 4

This Section Id has an enrollment of: 5

*********************************************************************

Course No: 240 Intro to the Basic Language with Section Id: 102  is taught by Wojick in the Course Section: 2

This Section Id has an enrollment of: 1

*********************************************************************

This input match has a total enrollment of: 7 students.

SQL&gt; @q4;

Enter the piece of the course description in UPPER case:<strong>JAVA</strong>

Enter the beginning of Instructor last name in UPPER CASE:<strong>S</strong>

Course No: 124 Advanced Java Programming with Section Id: 127  is taught by Schorin in the Course Section: 2

This Section Id has an enrollment of: 1

*********************************************************************

Course No: 122 Intermediate Java Programming with Section Id: 153  is taught by Smythe in the Course Section: 2

This Section Id has an enrollment of: 3

*********************************************************************

Course No: 120 Intro to Java Programming with Section Id: 150  is taught by Schorin in the Course Section: 5

This Section Id has an enrollment of: 3

*********************************************************************

This input match has a total enrollment of: 7 students.