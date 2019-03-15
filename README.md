## KRR Academic Advisor
## David, Itay, and Alex


# Our motivation
We wanted to create a KRR-powered course advising system for CS students. This can enable users to get a personalized list of courses available for the following quarter. Northwestern currently does not have a process for this, it's current methods are confusing and not personable to each user, all the while scheduling advising appointments with a human advisor may be a hassle.


# How it works
**Knowledge Representation**: We used the openCyc database through Companions to leverage existing data about Northwestern courses. This data is elaborated upon with some of our bespoke concepts such as:
* Main knowledge components:
	* StudentID -- Collection
	* studentIdentifier -- Predicate
	* courseTaken -- Predicate
	* CourseID -- Collection
	* courseIdentifier -- Predicate
	* coursePrereq -- Predicate
		* Courses with multiple prereqs are also accounted for
	* DegreeRequirement -- Collection
	* satisfiedRequirement -- Predicate
* Universal course identifiers to abstract from the quarter-specific information that already exists in the knowledgebase
* Create intricate relationships amongst the courses, as follows:
  * The degree requirements each of the courses fulfil in regards to the Computer Science major.
  * The prerequisites required by each of the courses in order to actually enroll in them.
  


# How to use
1. Start Companions on your computer. See EECS 371 Assignment 4 PDF for instructions on how to do this.
2. Enter a username and start a Companions session.
3. Right click on "interaction manager" and load list of specific flat files shown below.
4. Under the Collections:Predicate folder, load the "all-flats.krf" file into Companions.

**NOTE** You can use the student ID anr3485 for queries, as information about that student has already been put in the KB.

5. Open 'main.krf' in a text editor. This will act as a template
  1. Replace ENTER_NETID with your unique net id
  2. Replace ENTER_STUDENT_NAME with your full name
  3. For each course you have taken, complete the courseTaken predicate.
    * The first argument is your net id
    * The second argument is an EECS class you've take in the form EECSXXX, where XXX is the course number.
      * If there's a dash in the course name, add it as EECSXXX-X.
      * For all EECS 39X and EECS 49X courses, find the appropriate name from the list stored in 'main.krf'. Use this as the first argument, rather than just EECS39X/EECS49X.
6. Save the updated 'main.krf' and load this flatfile into Companions
7. Enter interaction manager by right clicking on it and choosing "Browse KB".
8. Navigate to Query tab
9. Choose one of the following queries, substituting out ENTER_NETID with your unique NetID.
	* (canTakeCourse ENTER_NETID ?courses)
		* Description: Provides a list of available courses for next quarter based on prereqs
	* (canTakeCourseByTopic ENTER_NETID ?CourseID ?Topic)
		* Description: Similar functionality to above query but lets user filter out by course topic
		* Topics include AI, Systems, Theory, Interfaces, SoftwareDevelopment, Project, TechnicalElective
	* (missingRequirements ENTER_NETID)
		* Description: Lists the degree requirements the student needs to fulfill
	* (satisfiedRequirement ENTER_NETID ?requirement)
		* Description: Returns all degree requirements satisfied by student
	* (sampleCourseSchedule ENTER_NETID ?courseList)
		* Description: Generates a sample course schedule for next quarter, taking into account the times for each course to prevent time clashes.
	* (canGraduate ENTER_NETID)
		* Description: Takes into account degree requirements to check whether the user can graduate or not.  
10. Press the button titled 'Query using fire:query'
11. Your results will appear in the query response window
