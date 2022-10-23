# masa-exam

**Part I: Theory**
*Please, do NOT use online resources as an assistance for this part of the exam*

**Section A: Please, select the correct answer or the most close to the correct one**

 1. What is a PR?
 - [ ] Program Result: the outcome of a programming effort available for testing
 - [ ] Public Relations: a practice of managing and influencing an organizational info to the public
 - [^] Pull Request: a request to review the code of a developer prior to merging it main branch
 - [ ] Private Role: A security role that is used in internal system processing

2. What is the role of a service in nodejs server architecture?
 - [ ] Get the request from the router, treat the request parameters, prepare the response of the server to the consumer
 - [^]  Keep state of a specific logic portion of the system, provide processing of the data passed from the different controllers, parse the data and returned the processed response
 - [ ] To be the first element in the system that should service the consumer for his CRUD request to the server
 - [ ] To provide services to the system that do not require a state but should be used across the whole system

3. What is INNER JOIN?
 - [ ] A mechanism to link between to tables in the SQL query to bring data based on the same value in two tables. Allows NULL values on one on the sides of the JOIN
 - [^] A mechanism to link between to tables in the SQL query to bring data based on the same value in two tables. Only non NULL values are accepted for both sides of the JOIN
 - [ ] A way of executing to `foreach` loops in JS/TS while the internal loop uses values of the external loop
 - [ ] Such a term does not exist

4. What is the code of a server error in HTTP protocol?
 - [ ] 2xx
 - [ ] 3xx
 - [ ] 4xx
 - [^] 5xx

5. What is the correct flow a story?
 - [ ] Software Detailed Design (SDD), Product design, QA review, UI design, Development, QA testing, Customer review
 - [^] Customer request, Product design, UI design, SDD, QA review, Development, QA testing, Customer User Acceptance Testing (UAT)
 - [ ] Product design, SDD, QA review, UI design, Development, QA testing, UAT
 - [ ] Customer request, UI design, Product design, UAT, QA review, Development, QA testing

6. Which tool would you use to test a nodejs server?
 - [ ] Browser
 - [ ] Postman
 - [ ] Fiddler
 - [^] All answers are correct

7. What is the most secure way to connect to SQL Server?
 - [^] Integrated security
 - [ ] Mixed mode
 - [ ] SQL Server login
 - [ ] Application role

8. What is the correct pair of a protocol and the port for secure HTTP communication?
 - [ ] HTTP:80
 - [ ] HTTPS:80
 - [ ] HTTPS:443
 - [^] HTTP:443

9. What is a trigger
 - [^] Trigger is a piece of code executed by the database engine whenever some action is performed on a database object like tables, view, etc.
 - [ ] Trigger is a method that is called JS/TS environment whenever a certain event is fired to complete an asynchronous code execution
 - [ ] Trigger is a processing being performed right after the merge of a code to main branch in order to run a build for the system
 - [ ] Trigger is the mechanism by which the router is sending its data to the controller in nodejs server

10. Why would you use the JWT token? (more than a single answer can be selected)
 - [ ] JWT tokens are encrypted
 - [^] It's a more secure way of handling authentication and authorization data than username and password
 - [^] JWT tokens are signed and this signature can be verified uniquely
 - [ ] All answers are correct

**Section B: Please, explain the following terms the best way you can**

11. Authentication & Authorization
In order to maintain security we use Authentication and Authorization
First step is Authentication: by it we verify the indentity (kinda enter the house)
Second step is Authorization: by it we are checking, does the user have permission to resoures (like after entering the house we are checking, can this user go to bathroom, or to bedroom, ect)

12. Stored procedure
There are two ways to interact with database - by query or by stored procedure
When we use query, we keep as a constand the whole query itself, insert paramerteres iside the fucntion and send it to database - so by using query we have more "power" as a developer to modify query, ect
When we use stored procedure, we keen as constand only the name of stored procedure, and the content of it (some combination of queries) is kept in the database and usualy was written by person who works with database (not developer). So as a developer, we send to database the name of stores procedure and params, and database insert this params to stored procedure by itself.

13. Git rebase
Git rebase is a way to combine two branches. 
There are two ways to do it: rebase and merge.
We prefer to use rebase, because it kinda rewrite the history in a way we want and keep "1 line" of commits.

14. Generics
This is type, which allows us to create for example functions who can work with similar types, but not one type. In this case during creating of the fuction we use generics, and during calling the fuction we mention which type exactly will be applied.

15. Middleware
This is a place (part of architecture), where we proceed some actions (usually Authentication & Authorization) before the actual request was started to execute. In our code, from routes we go to middlewhewre before we go to controllers, which allows us to check does user have a token itself and permission to proceed request that he sent, before we start to execute the request itself

 
**Part II: Practice on paper**
*No restrictions on online resources usage*

16. You received a bug stating the following: 
"Intermittently the following method results in a system getting stuck." 
You're required to find and fix the problem in this method:

		public  static  addMonths(date: Date, value: number): Date {
		    let expectedMonth: number = date.getMonth() + value;
		    if (expectedMonth  >  12) {
		        expectedMonth = expectedMonth % 12;
		    }
    
		    if (expectedMonth  <  0) {
		        expectedMonth += 12;
	        }
    
		    date.setMonth(date.getMonth() + value);

			if (date.getMonth() == expectedMonth) {
            	return date;
        	}

	        const daysToAdd: number = date.getMonth() >  expectedMonth ? -1 : 1;
	        while (date.getMonth() !== expectedMonth) {
		        date.setDate(date.getDate() + daysToAdd);
		    }
    
		    return  date;
	    }

17. Having the following DB tables diagram:
![](https://github.com/lentyaishe/masa-exam/blob/dev/resources/db-relations.jpg)

SELECT CONCAT(student.first_name, student.last_name) as Student, CONCAT(parent.first_name, parent.last_name, parent.phone) as Parent
FROM parent_to_student
INNER JOIN student ON parent_to_student.student_id = student.id
INNER JOIN parent ON parent_to_student.parent_id = parent.id

//I know it works not how it should be but it best I could do and I moved on for next task)
