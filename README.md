# KRR Academic Advisor
# David, Itay, and Alex

**Steps**:
1. Start Companions on your computer. See EECS 371 Assignment 4 PDF for instructions on how to do this.
2. Enter a username and start a Companions session.
3. Right click on "interaction manager" and load list of specific flat files shown below.
4. Under the Collections:Predicate folder, load the "all-flats.krf" file into Companions.
5. Open 'user-info.krf' in a text editor. This will act as a template
  1. Replace ENTER_NETID with your unique net id
  2. Replace ENTER_STUDENT_NAME with your full name
  3. For each course you have taken, complete the courseTaken predicate.
    * The first argument is your net id
    * The second argument is an EECS class you've take in the form EECSXXX, where XXX is the course number.
      * If there's a dash in the course name, add it as EECSXXX-X.
      * For all EECS 39X and EECS 49X courses, find the appropriate name from the list stored in 'user-info.krf'. Use this as the first argument, rather than just EECS39X/EECS49X.
6. Save the updated 'user-info.krf' and load this flatfile into Companions
7. Enter interaction manager by right clicking on it and choosing "Browse KB".
8. Navigate to Query tab
9. Type the query (canTakeCourse ENTER_NETID ?courses), substituting out ENTER_NETID with your unique net id.
10. Press the button titled 'Query using fire:query'
11. Your results will show up, look through the course names to decide which courses would be best for your 2019 Spring Quarter.
