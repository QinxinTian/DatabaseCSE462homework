# OracleSQL
Some Oracle SQL files
Project1 Project2 Project3


Project1:
You are given the following relational schema:
MOVIE(TITLE,DIR,YEAR,BUDGET,LANGUAGE)
CAST(TITLE,ACTOR)
REVIEW(CRITIC,TITLE,SCORE)
Keys are underlined. The attributes TITLE in CAST and REVIEW are foreign keys referencing MOVIE(TITLE).
You can assume that relation constants are available.
Problem 1 (12 pts, 6% of the final grade)
Write the following queries in relational algebra and SQL:
• 1.1: Find all the movies with maximum existing scores.
• 1.2: Find all the critics that reviewed all the movies directed by Spielberg, possibly except ”E.T.”.
Write the following queries in SQL:
• 1.3: For every director, list the director and the number of movies in French made by this director. If
a director has made no such movies, then the director should be listed with zero. The result should be
sorted in descending order.
• 1.4: Find all the actors whose average movie budget was greater than the average budget of Tom
Cruise’s movies.
Problem 2 (8 pts, 4% of the final grade)
You are supposed to write the following query
List all the critics, each with their average movie score.
in two different ways:
• 2.1: as a single SQL query. The calculation of the average score should by done by this query.
• 2.2: using JDBC to fetch each input tuple in turn. The calculation of the average score should be
done by the Java/JDBC program, not by SQL.
You can assume that there are at most 100 critics and 1000 movies. The submission instructions and the
iput/output formats will be provided.
Problem 3 (extra, 8 pts, 4% of the final grade)
Given the relation Hotel(Name,Price,Distance,Rating), the following dominance relation is defined between
hotels:
a hotel h1 = (n1, p1, d1, r1) dominates a hotel h2 = (n2, p2, d2, r2) iff the following two conditions
hold:
1. p1 ≤ p2 ∧ d1 ≤ d2 ∧ r1 ≥ r2, and
2. p1 < p2 ∨ d1 < d2 ∨ r1 > r2.
Write the following query in relational algebra and SQL:
find all hotels that are not dominated by any other hotel.



Project2:
CSE 462: Project #2 (due on April 13, 2017, at 23.55 ET)
This is an individual project: no cooperation, collaboration or copying is allowed.
Problem 1: E-R (10 points, 5% of the final grade)
You are given the following relational schema (keys underlined):
Flight(FlightNum,DepTime,ArrTime,OrigAirport,DestAirport)
Flight(OriginAirport) references Airport(Code)
Flight(DestinationAirport) references Airport(Code)
FlightInstance(FlightNum,Date)
FlightInstance(FlightNum) references Flight(FlightNum)
Passenger(PassName,PassAddress)
Booking(PassName,FlightNum,Date,Status)
Booking(PassName) references Passenger(PassName)
Booking(FlightNum,Date) references FlightInstance(FlightNum,Date)
Plane(PlaneId, Model)
Repaired(PlaneId,FromTime)
Repaired(PlaneId) references Plane(PlaneId)
Operational(PlaneId)
Operational(PlaneId) references Plane(PlaneId)
Allocated(PlaneId,FlightNum,Date)
Allocated(PlaneId) references Operational(PlaneId)
Allocated(FlightNum,Date) references FlightInstance(FlightNum,Date)
Airport(Code)
To do:
1. Decompile the above schema into an E-R schema representing the same information.
Problem 2: Relational database design (10 points, 5% of the final grade)
You are given the relation schema
Course Teacher Hour Room Student
and the functional dependencies:
Course → T eacher,
Hour Room → Course,
Hour T eacher → Room,
Hour Student → Room.
To do:
1. Is this schema in BCNF? Explain using appropriate definitions.
2. If R is not in BCNF, provide its lossless join decomposition into BCNF and determine whether
it preserves the given functional dependencies.
Problem 3: Extra credit (10 points, 5 % of the final grade)
The relation schema is R(A, B, C, D). FDs and MVDs are defined over this schema.
Are the following inferences correct? Prove or disprove them using formal definitions.
1. Does A → B follow from B → A?
2. Does C → B follow from AC → B and C → A?
3. Does A  C follow from AB  C?
4. Does A  D follow from A → C and A  B?




Project3:
Problem 1 (20 pts, 10% of the nal grade)
Suppose you have to represent in XML the information about students and their course grades in
the following way:
 student name (attribute). Assume each student has a dierent name.
 list of pairs (course,grade).
To do:
1. Dene the schema of the XML database containing the student grade information as a DTD
A.
2. Using the DTD A, two test XML documents provided separately (t1.xml and t2.xml) and
an online validation tool (www.xmlvalidation.com), validate the documents with respect to
the DTD A and report the results. Every violation, if there exists one, in the provided XML
les t1.xml and t2.xml has to be reported. Each violation should be explained and should
mention the line that caused the violation. If the validation tool does not provide all the
violations, you have to nd them yourself.
3. Write the following queries in XQuery:
(a) Find all the students that took CSE462 and their grades in that course.
(b) Find all the classes that had an average grade of at least 3.0.
The inputs of the queries are documents valid with respect to DTD A.
4. Install eXistdb (http://exist-db.org/exist/apps/homepage/index.html) on your com-
puter and evaluate the queries 1a and 1b above over the test XML document t1.xml, reporting
the results.
Problem 2, extra credit (20 pts, 10% of the nal grade)
Note: Assume that the input is a document valid with respect to the DTD A and each student has
a dierent name. To do:
1. Write an XQuery query QExtra whose input is a document valid with respect to DTD A and
whose output is an equivalent document in which the students (and their grades) are listed
under the courses they took. Dene a DTD B for that format.
