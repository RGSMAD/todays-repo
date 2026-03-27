🚀 How I’ll Teach You YAML (Structured Plan)

✅ Phase 1: Basics

What is YAML

Syntax (key-value, indentation)

Data types (Normal and Advanced)

Advanced Data types: 

&#x20; Lists \& dictionaries

&#x20; Nested structures

✅ Phase 2: Hands-on (Important)

Write your own YAML

Understand the YAML

Common errors and Fixing errors

Real GitHub Actions YAML breakdown

Multi-job pipelines

✅ Phase 3: Advanced (Real DevOps)

Matrix, Variables, reuse of variables (environment variables) \& Secrets

Conditional execution, context variables, inputs and outputs

Convert logic → YAML

Reusable workflows


✅ Phase 1: Basics

YAML (YAML Ain’t Markup Language) is a human-readable data serialization format used to represent structured data. It is commonly used for writing configuration files and enables easy storage, transfer, and processing of data by machines.

YAML:

❌ Markup Language

❌ Programming Language

❌ Scripting Language

✅ Data Serialization Format


✔ “Not a markup language”

&#x09;==> Not uses tags like HTML/XML

✔ “Not a programming language”

&#x09;==> Doesn't use Loops, Conditions, Functions

✔ “Not a scripting language”

&#x09;==> It is just for writing config, not an executable script.

✔ “Data Serialization Format looks like JSON”

&#x09;==> Used for writing config in structured data format(Key-Value pairs).

Does data serialisation language is something like writing the meaningful data in a serialized way I mean in a chronological order?


❌ “serialized = chronological order”

👉 Not correct

Serialization has nothing to do with time or order of events.


Serialization = Structuring data

NOT = Ordering data by time


✅ Simple Meaning of Data Serialization

Data serialization means converting data into a structured format so it can be easily stored, transferred, or processed.


Data serialization format: Raw information converted into structured data.


YAML = Structured Data Format + Configuration Language


Imagine you have this data in your mind:


Name: Madhav

Skills: AWS, Terraform



JSON:

\------

{

&#x20; "name": "Madhav",

&#x20; "skills": \["AWS", "Terraform"]

}


YAML:

\------

name: Madhav

skills: 

&#x20; - AWS

&#x20; - Terraform


Why do we need YAML?


👉 YAML is used to:

Represent data in structured way to save them in files and to send over network or to share between systems. So tools (GitHub Actions, Kubernetes, Terraform) can understand it.


YAML (Key-value based and Indentation):

Foundation of YAML lies in understanding the indentation-based structure and Key-value pairs.


Indentation:

\---------------

YAML becomes easy or painful based on just one thing → indentation.


YAML doesn't follow any tags like markup languages or any kind of braces like programming languages, it just follows indentation like python. Indentation is nothing but grouping the data as block by only using leading whitespaces, grouping the data with whitespaces before the data.


To be more clear, If two lines have same number of whitespaces before the starting position of data, they are said to be the data of same level.


Indentation = Structure = Relationship


It defines:

Parent → Child

Grouping

Hierarchy


More indentation = deeper level (child)

Less indentation = higher level (parent)


Ex:

\----

employee:

&#x20; name: Madhav

&#x20; experience:

&#x20;   years: 2.7


structure:

\-----------

employee (parent)

&#x20;├── name (first child)

&#x20;└── experience (second child)

&#x20;      └── years (child of second child)


Golden and standard rules of indentation:


✔ Rule 1: Use 2 spaces (standard)

&#x09;✔ 2 spaces → best practice

&#x09;❌ 1 or 3 → inconsistent


✔ Rule 2: Never use tabs (Number of spaces in tab differs with respect to file editors)

&#x09;❌ Tabs break YAML

&#x09;✔ Only spaces


✔ Rule 3: Align siblings

&#x09;In the above examples, name and experience are siblings. So, align them properly to say that they belong to same hierarchy and are siblings.


Key-Value pairs:

\-----------------

As said, all information in YAML is represented in Key-Value pairs, just like JSON, which means any raw information has a key and a value, where key describes what information it is and value defines the actual data.


In the above example employee information is being represented in YAML. So the root level key will be employee. And it has more information in the form of key-value pairs.


Firstly, name of the employee in the form of "name: Madhav" and then experience is another key containing few more key-value pairs, here it is only one i.e., years: 2.7


But, see the below example, the experience may contain more information.


employees:

&#x20; - name: Madhav

&#x20;   experience: 

&#x20;     years: 2.7


&#x20; - name: Jaspreet Bumrah

&#x20;   experience:

&#x20;     years: 14

&#x20;     role: premium-fast bowler

&#x20;     franchise: Mumbai Indians


Tree structure:

\----------------

employees

├── \[0]

│   ├── name: Madhav

│   └── experience

│       └── years: 2.7

│

└── \[1]

&#x20;   ├── name: Jaspreet Bumrah

&#x20;   └── experience

&#x20;       ├── years: 14

&#x20;       ├── role: premium-fast bowler

&#x20;       └── franchise: Mumbai Indians


Standard practice of Key-Value pairs in YAML:

Keys must always be in lower case followed by colon(:) and then a space and then values.


key: value


As said, each key will have values. But the values could be either string or numerical values or could be Boolean or could be set of strings or set of numbers or map of different key-value pairs called as objects. And these different types of values are called as data types.


Let's deep dive into different data types and how can we assign values of different data types to a key.


Data types in YAML:

\--------------------

1\. String:

name: Rajoli Girisai Madhav

city: Hyderabad


(or)


name: 'Rajoli Girisai Madhav'

city: 'Hyderabad'


(or)


name: "Rajoli Girisai Madhav"

city: "Hyderabad"


2\. Numbers(Integers, floating numbers):
number: 5
pi\_value: 3.14159
height\_meters: 1.85
negative\_value: -0.5

exponential numbers:

miles\_to\_sun: 12.3e+05
small\_value: 1.5e-15
large\_value: -3.14E+16

3\. Boolean(True or False):
is\_devops: true
is\_cloud: false

4\. List/array:
List or array is the set of items and items could be either strings or numbers.
Note: List are to be represented in a lower hierarchy level with same indentation followed by a hyphen(-) and space.

Ex:
skills:
&#x20; - AWS
&#x20; - Terraform
&#x20; - GitHub Actions
&#x20; - CI/CD
&#x20; - YAML

5\. Object //Map / Dictionary:
Dictionary or object or map all refers to same thing. 
In general, a key-value pair is considered as a object. And group of such objects is called a map or a dictionary.

Ex:
employee:
&#x20; name: Madhav
&#x20; role: DevOps Engineer

6\. list(objects): If a key has nested list, where each list is a map/objects and then it is called as list(objects).
Ex:
employees:
&#x20; - name: Madhav
&#x20;   experience: 2.7 years
&#x20;   role: DevOps Engineer

&#x20; - name: Raghav
&#x20;   experience: 6 years
&#x20;   role: Backend Developer

&#x20; - name: Manisha
&#x20;   experience: 15.3 years
&#x20;   role: Full stack Engineer


7\. map(objects) or object(map):
It means map of different objects.

Ex:
\----
employees:
&#x20; Madhav:
&#x20;   experience: 2.7 years
&#x20;   role: DevOps Engineer

&#x20; Raghav:
&#x20;   experience: 6 years
&#x20;   role: Backend Developer

&#x20; Manisha:
&#x20;   experience: 15.3 years
&#x20;   role: Full stack Engineer


8\. Nested structures: You can club different type of data types together to form a nested structure.

Ex:
employees:
&#x20; - name: Madhav
&#x20;   experience:
&#x20;     years: 2.7
&#x20;     role: Mainframe\_engineer
&#x20;   skills:
&#x20;     - AWS cloud essentials
&#x20;     - CI/CD
&#x20;     - Terraform
&#x20;     - GitHub Actions
&#x20;   is\_devops\_engineer: false
&#x20;   willing\_to\_become\_devops\_engineer: true

&#x20; - name: Jaspreet Bumrah
&#x20;   experience:
&#x20;     years: 14
&#x20;     role: premium-fast bowler
&#x20;     franchise: Mumbai Indians

In the above example, you have string, numbers, boolean, list, objects and map(objects) all together and became one single nested list and its tree structure is as follows.

employees
├── \[0]
│   ├── name: Madhav
│   ├── experience
│   │   ├── years: 2.7
│   │   └── role: Mainframe\_engineer
│   ├── skills
│   │   ├── \[0]: AWS cloud essentials
│   │   ├── \[1]: CI/CD
│   │   ├── \[2]: Terraform
│   │   └── \[3]: GitHub Actions
│   ├── is\_devops\_engineer: false
│   └── willing\_to\_become\_devops\_engineer: true
│
└── \[1]
    ├── name: Jaspreet Bumrah
    └── experience
        ├── years: 14
        ├── role: premium-fast bowler
        └── franchise: Mumbai Indians

---

✅ Phase 2: Hands-on (Important)

Write your own workflow YAML:
\------------------------------

Ex-1: 👉 Write YAML for:

Project name: 3-tier-app
Environments: dev, prod
Each environment has region:
dev → ap-south-1
prod → us-east-1

Ans:
method-1:
\----------

project\_name: 3-tier-app
environments: 
&#x20; - name: dev
&#x20;   region: ap-south-1
&#x20; - name: prod
&#x20;   region: us-east-1

Breakdown of example:



project\_name and environments are two top-level keys and project\_name is of string type, whereas environments is list(objects). And the objects are name and region, both are of string type, in each list item.







method-2: (preferred mostly)

\----------

project\_name: 3-tier-app



environments:

&#x20; dev:

&#x20;   region: ap-south-1

&#x20; prod:

&#x20;   region: us-east-1





Breakdown of example:



project\_name and environments are two top-level keys and project\_name is of string type, whereas environments is map(objects). And the objects are region, a string type object.







Ex-2: 👉 Write YAML for:



Note: Take 3 students information and do the below example. (self-practice) and Also, by using AI tools, try to generate a Tree structure of your YAML file to see your where your yaml structure goes wrong.

name → name\_of\_student

education: list(objects) or nested objects

(Highest degree, college name, percentage, passed out year)  --> Write twice for both PG \& UG, if PG is your highest qualification

(Intermediate/Diploma, college name, percentage)

(S.S.C, school name, percentage)

Skills:

(Add all your skills), if required add ratings for yourself out of 10.







students:

&#x20; - name: Madhav

&#x20;   education:

&#x20;     b.tech:

&#x20;       college\_name: "Sri Venkateswara College of Engineering, Kadapa"

&#x20;       percentage: 77.21

&#x20;       passed\_out: 2021



&#x20;     intermediate:

&#x20;       college\_name: "Narayana Junior College, Kadapa"

&#x20;       percentage: 91.9



&#x20;     ssc:

&#x20;       school\_name: "Pavan E.M./T.M. High School, Kadapa"

&#x20;       gpa: 9.2



&#x20;   skills:

&#x20;     - AWS cloud essentials

&#x20;     - Linux

&#x20;     - Terraform

&#x20;     - CI/CD concepts

&#x20;     - GitHub Actions

&#x20;     - YAML



&#x20; - name: Nithya pooja reddy

&#x20;   education:

&#x20;     b.tech:

&#x20;       college\_name: "Sri Venkateswara College of Engineering, Kadapa"

&#x20;       percentage: 82

&#x20;       passed\_out: 2021



&#x20;     intermediate:

&#x20;       college\_name: "Narayana Junior College, Kadapa"

&#x20;       percentage: 89



&#x20;     ssc:

&#x20;       school\_name: "Saibaba High School, Kadapa"

&#x20;       gpa: 9.5



&#x20;   skills:

&#x20;     - Testing Automation

&#x20;     - Selenium



&#x20; - name: Prasad

&#x20;   education:

&#x20;     b.tech:

&#x20;       college\_name: "Sri Venkateswara College of Engineering, Kadapa"

&#x20;       percentage: 74

&#x20;       passed\_out: 2021



&#x20;     intermediate:

&#x20;       college\_name: "Sri Chaitanya Junior College, Kadapa"

&#x20;       percentage: 85



&#x20;     ssc:

&#x20;       school\_name: "Gowri Shakar High School, Kadapa"

&#x20;       gpa: 9.0



&#x20;   skills:

&#x20;     - HTML

&#x20;     - CSS

&#x20;     - Java Script

&#x20;     - Python







Tree structure of above YAML:

\-----------------------------



students

├── \[0]

│   ├── name: Madhav

│   ├── education

│   │   ├── b.tech

│   │   │   ├── college\_name: Sri Venkateswara College of Engineering, Kadapa

│   │   │   ├── percentage: 77.21

│   │   │   └── passed\_out: 2021

│   │   ├── intermediate

│   │   │   ├── college\_name: Narayana Junior College, Kadapa

│   │   │   └── percentage: 91.9

│   │   └── ssc

│   │       ├── school\_name: Pavan E.M./T.M. High School, Kadapa

│   │       └── gpa: 9.2

│   └── skills

│       ├── AWS cloud essentials

│       ├── Linux

│       ├── Terraform

│       ├── CI/CD concepts

│       ├── GitHub Actions

│       └── YAML

│

├── \[1]

│   ├── name: Nithya pooja reddy

│   ├── education

│   │   ├── b.tech

│   │   │   ├── college\_name: Sri Venkateswara College of Engineering, Kadapa

│   │   │   ├── percentage: 82

│   │   │   └── passed\_out: 2021

│   │   ├── intermediate

│   │   │   ├── college\_name: Narayana Junior College, Kadapa

│   │   │   └── percentage: 89

│   │   └── ssc

│   │       ├── school\_name: Saibaba High School, Kadapa

│   │       └── gpa: 9.5

│   └── skills

│       ├── Testing Automation

│       └── Selenium

│

└── \[2]

&#x20;   ├── name: Prasad

&#x20;   ├── education

&#x20;   │   ├── b.tech

&#x20;   │   │   ├── college\_name: Sri Venkateswara College of Engineering, Kadapa

&#x20;   │   │   ├── percentage: 74

&#x20;   │   │   └── passed\_out: 2021

&#x20;   │   ├── intermediate

&#x20;   │   │   ├── college\_name: Sri Chaitanya Junior College, Kadapa

&#x20;   │   │   └── percentage: 85

&#x20;   │   └── ssc

&#x20;   │       ├── school\_name: Gowri Shakar High School, Kadapa

&#x20;   │       └── gpa: 9.0

&#x20;   └── skills

&#x20;       ├── HTML

&#x20;       ├── CSS

&#x20;       ├── Java Script

&#x20;       └── Python





Understand the YAML:

\---------------------



Ex-1: Understand this YAML:



servers:

&#x20; - name: web-server

&#x20;   ip: 10.0.0.1

&#x20; - name: app-server

&#x20;   ip: 10.0.0.2



🎯 Your Task



Explain:



* What is servers
* What does - represent
* How many items are there
* What each item contains





Ans:

* Servers is a top-level key containing a list of objects.
* "-" represents an item inside the top-level key servers.
* There are two different items (web and app servers) in the form of objects.
* Each item contains two different objects whose keys are name and ip.





Ex-2: Try this out and answer the questions.



company:

&#x20; name: TechNova



&#x20; departments:

&#x20;   - name: Engineering

&#x20;     employees:

&#x20;       - name: Madhav

&#x20;         skills:

&#x20;           - Terraform

&#x20;           - AWS

&#x20;           - GitHub Actions

&#x20;         experience:

&#x20;           years: 2.7

&#x20;           level: junior



&#x20;       - name: Raghav

&#x20;         skills:

&#x20;           - Java

&#x20;           - Spring Boot

&#x20;         experience:

&#x20;           years: 6

&#x20;           level: senior



&#x20;   - name: HR

&#x20;     employees:

&#x20;       - name: Manisha

&#x20;         skills:

&#x20;           - Recruitment

&#x20;           - Communication

&#x20;         experience:

&#x20;           years: 5

&#x20;           level: mid



&#x20; is\_remote\_friendly: true





Questions:



🧠 Your Tasks



Try answering these (don’t scroll ahead mentally, actually think 😄):



1. What is the type of company?
2. What is the type of departments?
3. What is the type of each item inside departments?
4. What is the type of employees?
5. What is the type of skills?
6. What is the type of experience?

7. Overall, how would you describe:



departments → employees → skills



in one line (type chain)





Answers:



1\. type of company is object(map) or object(mixed types).

2\. type of departments is list(objects).

3\. type of each item in departments is object / map / dictionary

4\. type of employees is list(objects).

5\. type of skills is a list of strings.

6\. type of experience is object / map / dictionary.

7\. departments → list of objects → employees → list of objects → skills → list of strings

i.e., departments are list of employee objects working in different departments and employee objects are also the list of objects with employee data including skills, which are list of strings. 







Common errors in YAML and Fixing them:-

\--------------------------------------

1\. Indentation Issues (MOST COMMON): Indentation in YAML is most sensitive. one indentation error leads to change in structure of data.



✅ To fix this, always use the above specified golden rules, make them as standard practice.

They are:

✔ Rule 1: Use 2 spaces (standard)

✔ Rule 2: Never use tabs (Number of spaces in tab differs with respect to file editors)

✔ Rule 3: Align siblings with same indentation





2\. Mixing of tab spaces and normal whitespaces.



✅ To fix this, Never use tabs, if used, then change all spaces to tab. Never mess your YAML with mixed tab spaces and normal spaces.





3\. Duplicate Keys:

Ex:

employee:

&#x20; name: Madhav

&#x20; name: Raghav   # ❌ duplicate key

If you use duplicate keys, YAML parsers may:

* overwrite silently 😬
* or throw error



✅ To fix this, make use of advanced data types to get rid of duplicate keys. And try to check the tree like structure of your YAML to ensure that you have structured your data correctly.

⚠️ Note: Make sure to use correct data type: list, objects, list(objects), map(objects), nested structures. 





4\. Incorrect Key-Value Formatting: Missing space after colon.

Ex:

name:Madhav   # ❌ missing space



✅ Remember that a key-value pair must always be separated with a colon followed by a space.

✅ name: Madhav





5\. Unquoted Special Values and Colon inside Values:

a) Unquoted Special Values

value: yes     # ⚠️ interpreted as boolean true

value: no      # ⚠️ false

value: on      # ⚠️ true



✅ If your values like yes, no, on etc., are representing special values like Boolean values you must specify them in quotes.



Ex: manual\_approval\_needed: "yes"	# ⚠️ interpreted as boolean true



b) Colon inside Values

Ex:

time: 10:30   # ⚠️ can break parsing



✅ time: "10:30"

✅ If your values had colons in between them, try to specify the values inside quotes, which says, consider it as a single value for that key.





6\. Multi-line Strings:

Ex:

message: Hello

&#x20; World   # ❌ invalid



⚠️ If you wish to input a value for a key as a multi line string, you have to follow a particular syntax.

Syntax:

message: |

&#x20; Hello

&#x20; World		# ✅ Valid



Ques: How to break multi-line string or how to end multi-line strings?



Ans: There is no special character needed to end multi-line strings. But, If you want to write multi line strings or break single-line to multi line strings, we can add different symbols.





🔥 Different ways to handle multi-line strings



1\. | (Literal — preserve line breaks)

Ex:

\-----

text: |

&#x20; Hello

&#x20; World



Output:

\---------

Hello

World



2\. > (Folded — joins lines)

Ex:

\-----

text: >

&#x20; Hello

&#x20; World



Output:

\----------

Hello World



3\. -/+ (adding or removing new lines at the end)

No new line gets added if you specify - after | or >

Ex-1: 

\------

text: |-

&#x20; Hello

&#x20; World



Output:

\---------

Hello

World



Ex-2:

\------

text: >-

&#x20; Hello

&#x20; World



Output:

\----------

Hello World



A new line gets added if you specify + after | or >

Ex-3:

\------

text: |+

&#x20; Hello

&#x20; World



Output:

\---------

Hello

World

<New\_empty\_line>



Ex-4:

\------

text: >+

&#x20; Hello

&#x20; World



Output:

\----------

Hello World

<New\_empty\_line>



Ques: What if you specifically added a new line after specifying either - or + after | or >.



Ex-5:

\------

text: |-

&#x20; Hello

&#x20; World

&#x20; <New\_empty\_line>



Output:

\---------

Hello

World



Ex-6:

\------

text: |+

&#x20; Hello

&#x20; World

&#x20; <New\_empty\_line>



Output:

\----------

Hello World

<New\_empty\_line>

<New\_empty\_line>



Ex-7:

\------

text: >-

&#x20; Hello

&#x20; World

&#x20; <New\_empty\_line>



Output:

\---------

Hello

World



Ex-8:

\------

text: >+

&#x20; Hello

&#x20; World

&#x20; <New\_empty\_line>



Output:

\----------

Hello World

<New\_empty\_line>

<New\_empty\_line>



Finally, conclusion:



| --> To preserve formatting (spaces or new lines)

> --> To remove new line formatting, to join the multi-line strings with a space in between.



adding - with | or > --> removes all empty lines at the end of multi-line string output, even if you specify an empty line intentionally.



adding + with | or > --> adds a new empty line at the end of multi-line string output. If you specify an empty line intentionally at the end of multi-line string, it will add another empty line under the output of multi-line string as shown in Example-6 and Example-8.



⚠️ Note: Never make use of combining | and > and adding multiple | and > for one key.



Ex:

\-----

text: |

&#x20; Hello >

&#x20; world |

&#x20; I am >

&#x20; Madhav

key\_name: YAML



or



text: |

&#x20; Hello |

&#x20; world |

&#x20; I am |

&#x20; Madhav

key\_name: YAML



or



text: >

&#x20; Hello >

&#x20; world >

&#x20; I am >

&#x20; Madhav

key\_name: YAML



All these examples are invalid and throws error while parsing.





Ques: Is this the correct syntax of YAML. I mean adding spaces in the keys.



YAML-example:



employee details:

&#x20; employee name: Madhav

&#x20; employee age: 25

&#x20; employee highest qualification: Bachelors degree



Ans:



Yes 👍 — your YAML is syntactically correct, it will allow spaces in keys as well. But it is not recommended as a best practice.



It throws error while converting the YAML structure to other formats. Since, some applications need the data to be given in other formats and so, it will be converted.



It is recommended to use either snake case or camel case:



snake case of above YAML-example:



employee\_details:

&#x20; employee\_name: Madhav

&#x20; employee\_age: 25

&#x20; employee\_highest\_qualification: Bachelors degree





camel case of above YAML-example:



employeeDetails:

&#x20; employeeName: Madhav

&#x20; employeeAge: 25

&#x20; employeeHighestQualification: Bachelors degree







Real GitHub Actions YAML breakdown:

\--------------------------------------



Ex-1:

\------

name: CI Pipeline



on: push



jobs:

&#x20; build:

&#x20;   runs-on: ubuntu-latest

&#x20;   steps:

&#x20;     - name: Print message

&#x20;       run: echo "Hello Madhav"





We know that GitHub Actions contains workflows, which contain jobs that executes or triggered by an Event and the job contains steps and the jobs will run on a runner.



Now Let's breakdown the above YAML file, which is a CI pipeline.



👉 The workflow is named "CI Pipeline" and is triggered on push events.



👉 At the top level, the YAML contains three keys:



* name → string
* on → event in the form of string
* jobs → map of job objects



👉 The jobs section:



* is a map of job objects
* each job (build) is an object



Each job contains:



* string fields (runs-on)
* steps → list of objects



👉 Each step:



* is an object
* contains keys like:

  * name → string
  * run → string



Understand the YAML workflow:



When code is pushed to the repository, the "CI Pipeline" workflow is triggered. The build job runs on a GitHub-hosted Ubuntu runner, where it executes the defined steps. In this case, it runs a command that prints "Hello Madhav" in the console output.



Workflow

&#x20;├── name

&#x20;├── trigger (on)

&#x20;└── jobs

&#x20;     └── build

&#x20;          ├── runner

&#x20;          └── steps

&#x20;               └── step1 (display "Hello Madhav" on runner)







Ex-2: (Multi-Job Pipelines)

\-----------------------------

Here's a another sample CI/CD pipeline(YAML) for provisioning infrastructure in AWS, that can be added in GitHub Actions



YAML-CI/CD Pipeline using Terraform:



name: Terraform CI/CD Pipeline



on:

&#x20; push:

&#x20;   branches: \[ "main" ]



jobs:

&#x20; terraform-ci:

&#x20;   name: Terraform CI

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - name: Checkout Code

&#x20;       uses: actions/checkout@v3



&#x20;     - name: Setup Terraform

&#x20;       uses: hashicorp/setup-terraform@v2



&#x20;     - name: Terraform Init

&#x20;       run: terraform init



&#x20;     - name: Terraform Format

&#x20;       run: terraform fmt -check



&#x20;     - name: Terraform Validate

&#x20;       run: terraform validate



&#x20;     - name: Terraform Plan

&#x20;       run: terraform plan



&#x20; terraform-cd:

&#x20;   name: Terraform Apply

&#x20;   needs: terraform-ci

&#x20;   runs-on: ubuntu-latest

&#x20;   environment: production   # 🔥 enables approval



&#x20;   steps:

&#x20;     - name: Checkout Code

&#x20;       uses: actions/checkout@v3



&#x20;     - name: Setup Terraform

&#x20;       uses: hashicorp/setup-terraform@v2



&#x20;     - name: Terraform Init

&#x20;       run: terraform init



&#x20;     - name: Terraform Apply

&#x20;       run: terraform apply -auto-approve







We know that GitHub Actions contains workflows, which contain jobs that executes or triggered by an Event and the job contains steps and the jobs will run on a runner.



Now Let's breakdown the above YAML file, which is a CI/CD pipeline.





👉 The workflow is named "Terraform CI/CD Pipeline" and is triggered on push events to the main branch.



👉 At the top level, the YAML contains three keys:



* name → string
* on → map (event configuration)
* jobs → map of job objects



👉 The on section:



* is a map
* contains push → which is also a map
* branches → list of strings



👉 The jobs section:



* is a map of job objects
* each job (terraform-ci, terraform-cd) is an object



Each job contains:



* string fields (name, runs-on)
* steps → list of objects



👉 Each step:



* is an object
* contains keys like:

  * name → string
  * uses or run → string



👉 Execution flow:



* terraform-ci runs first
* terraform-cd runs after (needs: terraform-ci)
* each job runs on a separate Ubuntu VM runner







Tree structure:

\----------------

root (map)

├── name (string)

│   └── "Terraform CI/CD Pipeline"

│

├── on (map)

│   └── push (map)

│       └── branches (list)

│           └── \[0] (string) → "main"

│

└── jobs (map)

&#x20;   ├── terraform-ci (object/map)

&#x20;   │   ├── name (string) → "Terraform CI"

&#x20;   │   ├── runs-on (string) → "ubuntu-latest"

&#x20;   │   └── steps (list)

&#x20;   │       ├── \[0] (object)

&#x20;   │       │   ├── name (string) → "Checkout Code"

&#x20;   │       │   └── uses (string) → "actions/checkout@v3"

&#x20;   │       │

&#x20;   │       ├── \[1] (object)

&#x20;   │       │   ├── name (string) → "Setup Terraform"

&#x20;   │       │   └── uses (string) → "hashicorp/setup-terraform@v2"

&#x20;   │       │

&#x20;   │       ├── \[2] (object)

&#x20;   │       │   ├── name (string) → "Terraform Init"

&#x20;   │       │   └── run (string) → "terraform init"

&#x20;   │       │

&#x20;   │       ├── \[3] (object)

&#x20;   │       │   ├── name (string) → "Terraform Format"

&#x20;   │       │   └── run (string) → "terraform fmt -check"

&#x20;   │       │

&#x20;   │       ├── \[4] (object)

&#x20;   │       │   ├── name (string) → "Terraform Validate"

&#x20;   │       │   └── run (string) → "terraform validate"

&#x20;   │       │

&#x20;   │       └── \[5] (object)

&#x20;   │           ├── name (string) → "Terraform Plan"

&#x20;   │           └── run (string) → "terraform plan"

&#x20;   │

&#x20;   └── terraform-cd (object/map)

&#x20;       ├── name (string) → "Terraform Apply"

&#x20;       ├── needs (string) → "terraform-ci"

&#x20;       ├── runs-on (string) → "ubuntu-latest"

&#x20;       ├── environment (string) → "production"

&#x20;       └── steps (list)

&#x20;           ├── \[0] (object)

&#x20;           │   ├── name (string) → "Checkout Code"

&#x20;           │   │   └── uses (string) → "actions/checkout@v3"

&#x20;           │

&#x20;           ├── \[1] (object)

&#x20;           │   ├── name (string) → "Setup Terraform"

&#x20;           │   │   └── uses (string) → "hashicorp/setup-terraform@v2"

&#x20;           │

&#x20;           ├── \[2] (object)

&#x20;           │   ├── name (string) → "Terraform Init"

&#x20;           │   │   └── run (string) → "terraform init"

&#x20;           │

&#x20;           └── \[3] (object)

&#x20;               ├── name (string) → "Terraform Apply"

&#x20;               └── run (string) → "terraform apply -auto-approve"

&#x20;  



\---------------------------------------------------------------------------------------------------------------------





✅ Phase 3: Advanced (Real DevOps):



Matrix, Variables, reuse of variables (environment variables) \& Secrets:

\-------------------------------------------------------------------------



Matrix: In GitHub Actions, a matrix lets you run the same job multiple times with different configurations.



Ex:

name: non-Matrix Example



on: push



jobs:

&#x20; test1:

&#x20;   runs-on: ubuntu-latest

&#x20;   with node-version: 16



&#x20;   steps:

&#x20;     - name: Print Node version

&#x20;       run: echo "Testing on Node ${{ node-version }}"



&#x20; test2:

&#x20;   runs-on: ubuntu-latest

&#x20;   with node-version: 18



&#x20;   steps:

&#x20;     - name: Print Node version

&#x20;       run: echo "Testing on Node ${{ node-version }}"



&#x20; test3

&#x20;   runs-on: ubuntu-latest

&#x20;   with node-version: 20



&#x20;   steps:

&#x20;     - name: Print Node version

&#x20;       run: echo "Testing on Node ${{ node-version }}"





Same example with matrix.



name: Matrix Example



on: push



jobs:

&#x20; test:

&#x20;   runs-on: ubuntu-latest



&#x20;   strategy:

&#x20;     matrix:

&#x20;       node-version: \[16, 18, 20]



&#x20;   steps:

&#x20;     - name: Print Node version

&#x20;       run: echo "Testing on Node ${{ matrix.node-version }}"





environment variables:

\-----------------------

In GitHub Actions, variables help you avoid repetition. variables are those whose values are changing continuously.



benefit of environment variables(variables \& reuse):

Define once → use multiple times

Change once → used everywhere (change in all places of usage at once)



Ex:

name: Variables Example



on: push



jobs:

&#x20; test:

&#x20;   runs-on: ubuntu-latest

&#x20;   env:

&#x20;     MESSAGE: "Learning DevOps"

&#x20;   steps:

&#x20;     - name: Print message

&#x20;       run: echo $MESSAGE



&#x20;     - name: Ask Question

&#x20;       run: echo "Hey varun, Are you "$MESSAGE"?"





Secrets:

\---------

Secrets are required for storing credentials and sensitive data like AWS keys, tokens, passwords etc.,



👉 Used for:



* AWS keys
* Tokens
* Passwords





⚠️ Key Rule



❌ Secrets are NOT stored in YAML

✅ They are stored in GitHub UI



To fetch secrets from Github UI to YAML:



run: echo ${{ secrets.MY\_SECRET }}



Ex:

&#x20;   steps:

&#x20;     - name: Setup SSH

&#x20;       uses: webfactory/ssh-agent@v0.7.0

&#x20;       with:

&#x20;         ssh-private-key: ${{ secrets.SSH\_PRIVATE\_KEY }}



Environment variables v/s secrets:

\-----------------------------------

| Feature         | env      | secrets       |

| --------------- | -------  | -----------   |

| Visible in code | ✅ Yes   | ❌ No        |

| Secure          | ❌ No    | ✅ Yes       |

| Use case        | configs  | credentials   |







Conditions in YAML:

\--------------------



Firstly, let's see why do we need conditions. Just assume in this way, what if you have 5 jobs in one CI/CD pipeline and 3+ events to trigger a workflow. But two of the jobs must execute only during one event occurred. but on those 2 jobs, other 3 are dependent. Then, how can you control those two jobs to execute only on those events.



So, we need conditions to have a control over the jobs for smooth processing of the workflow. If anything messy occurred, then the complete pipeline fails.



So, now a question arises, saying how to control them and what are the different conditions we can apply in the CI/CD?



Ans: As said, Conditions are required to control the jobs in workflow. And, the condition we use in GitHub Actions, mostly is if condition. We can use multiple conditions within if with help of logical operators and a condition can either be applied on either a job or on a step in GitHub Actions.





Let's see the syntax of if condition:



if: ${{ github.event\_name == 'push' }}		==> when a push event is triggered, the job or step executes.

if: ${{ github.event\_name == 'push' \&\& github.ref == 'refs/heads/main' }}  ==> Multiple conditions

if: ${{ github.event\_name == 'push' || github.event\_name == 'pull\_request' }}  ==> Multiple conditions



How to add them in a job or a step of an workflow.





job-level condition:

\----------------------

jobs:

&#x20; deploy:

&#x20;   if: ${{ github.ref == 'refs/heads/main' }}

&#x20;   runs-on: xxxx

&#x20;   steps:

&#x20;     - name: xxxx

&#x20;       uses: 

&#x20;     - name: yyyy

&#x20;       run: 







step-level condition:

\----------------------

jobs:

&#x20; deploy:

&#x20; runs-on: xxxxx

&#x20; steps:

&#x20;   - name: Run only on push

&#x20;     if: ${{ github.event\_name == 'push' }}

&#x20;     run: echo "This runs only on push"







Now, questions arises on your mind:



On what things, conditions can be arised. And what are github.event\_name, github.ref? And what are the values of them and what are they teaching us?



On what basis, we use conditions?





Answers for all these are given below.





github.event\_name, github.ref etc., are the context variables and by using them we can apply conditions on jobs or on steps of the workflow.



context variables:

\-------------------

context variables are those, by which we can apply conditions or which we can use them as variables that can be fetched for inputs and outputs.



And we have many such context variables, let's see what are they and what they are conveying to us.



1. github.event\_name: This context variable is used to convey about the event that triggers the workflow. By using this, we can apply conditions on the job/steps, on what event the workflow should get triggered or when it should not.



Basically, the event\_names like push, pull\_request etc., are used as values for github.event\_name.





| Event           | Value               |

| --------------- | ------------------- |

| Push            | `push`              |

| Pull Request    | `pull\_request`      |

| Manual trigger  | `workflow\_dispatch` |

| Schedule (cron) | `schedule`          |

| Release         | `release`           |







Ex:



push:

\------

steps:

&#x20; - name: Run on push only

&#x20;   if: ${{ github.event\_name == 'push' }}

&#x20;   run: echo "This runs only on push"



pull\_Request:

\--------------

steps:

&#x20; - name: PR validation

&#x20;   if: ${{ github.event\_name == 'pull\_request' }}

&#x20;   run: echo "Running PR checks"



Manual trigger:

\----------------

on:

&#x20; workflow\_dispatch:



jobs:

&#x20; deploy:

&#x20;   if: ${{ github.event\_name == 'workflow\_dispatch' }}

&#x20;   runs-on: ubuntu-latest



schedule (cron): runs only on scheduled jobs

\-----------------

on:

&#x20; schedule:

&#x20;   - cron: "0 0 \* \* \*"



jobs:

&#x20; nightly:

&#x20;   if: ${{ github.event\_name == 'schedule' }}

&#x20;   runs-on: ubuntu-latest







👉 This is a cron expression with 5 fields



“The cron expression defines a time-based schedule for triggering workflows, using a 5-field format representing minute, hour, day, month, and weekday in UTC.”



✅ Breakdown

0 0 \* \* \*

│ │ │ │ │

│ │ │ │ └── every day of week

│ │ │ └──── every month

│ │ └────── every day of month

│ └──────── hour = 0 (midnight)

└────────── minute = 0





Real-world scenario:



┌──────── minute (0–59)

│ ┌────── hour (0–23)

│ │ ┌──── day of month (1–31)

│ │ │ ┌── month (1–12)

│ │ │ │ ┌ day of week (0–7) (Sun = 0 or 7)

│ │ │ │ │

\* \* \* \* \*



Ex:



\*/10 9-17 \* \* 1-5

Runs every 10 minutes,

between 9 AM and 5 PM (UTC),

ONLY on Monday to Friday





release:

\---------

steps:

&#x20; - name: Run only on release

&#x20;   if: ${{ github.event\_name == 'release' }}

&#x20;   run: echo "Triggered by release event"



release again have different types for adding conditions.



| Action      | Meaning                            |

| ----------- | ---------------------------------- |

| `published` | Release is published ✅ (most used) |

| `created`   | Draft created                      |

| `edited`    | Release updated                    |

| `deleted`   | Release deleted                    |



If you wish to add condition based on type of release:



release action: (github.event.action ✅  github.event\_name ❌)

\-----------------------------------------------------------------

name: Release Pipeline



on:

&#x20; release:

&#x20;   types: \[ published, created, edited, deleted ]



jobs:

&#x20; deploy:

&#x20;   if: ${{ github.event.action == 'published' }}

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - name: Deploy only on published

&#x20;       run: echo "Deploying production release..."







2\. github.ref: This context variable is used to give the reference path (full path) of a branch or a tag used in the CI/CD pipeline. we can even restrict/allow the workflow to execute only on certain branches or branches with certain tags.



🔹 1. When pushing to main:

github.ref = refs/heads/main

if: ${{ github.ref == 'refs/heads/main' }}



🔹 2. When pushing to another branch

github.ref = refs/heads/branch\_name



🔹 3. When using tags

github.ref = refs/tags/v1.0		==> v1.0 is tag

if: startsWith(github.ref, 'refs/tags/')



🔹 4. For pull requests (IMPORTANT ⚠️)

github.ref = refs/pull/123/merge





3\. github.ref\_name: It requires only branch\_name on which the event occurred that triggering the workflow.



Ex: if: ${{ github.ref\_name == 'main' }}



4\. github.actor: It requires the username as input value. which means only for that user, the github actions workflow acts differently.

Ex:

if: ${{ github.actor == 'xxxxxx' }}

if: ${{ github.actor != 'yyyyy' }}



5\. github.repository: can add a condition that the job/step in a workflow works only for that repo.

Ex:

jobs:

&#x20; deploy:

&#x20;   if: ${{ github.repository == 'madhav-devops/terraform-project' }}

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - run: echo "Running only for this repository"





🔥 This condition can also prevent forked repo workflow execution.

Ex:

if: ${{ github.repository == 'original-owner/repo-name' }}



👉 Useful in:



* Open-source projects
* Security control







6\. github.sha: It represents full unique commit ID. Based on the commit ID also, we can make conditions.

Ex:

if: ${{ github.sha != '' }}	==> For every commit/event, pull request/push/release/workflow\_dispatch etc., it becomes true and will execute the job/step.





These 6 contexts are the most commonly used for conditions. Not only for conditions, they can also be used for fetching the data and printing/using them in job/steps.



Ex-1:

steps:

&#x20; - name: Print release info

&#x20;   run: |

&#x20;     echo "Tag: ${{ github.event.release.tag\_name }}"

&#x20;     echo "Name: ${{ github.event.release.name }}"





Ex-2:

on:

&#x20; release:

&#x20;   types: \[ published ]



jobs:

&#x20; deploy:

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - name: Deploy specific version

&#x20;       run: |

&#x20;         echo "Deploying version ${{ github.event.release.tag\_name }}"





Ex-3:

steps:

&#x20; - name: Deploy commit

&#x20;   run: |

&#x20;     echo "Deploying version ${{ github.sha }}"





Now, its time for looking at other conditions.



1. Based on the environmental variables defined, we can apply conditions.

Note: we'll be looking into environmental variables further in detail. As of now, just have a look at the condition, how, it is implemented.

Ex:

env:

&#x20; ENVIRONMENT: prod

if: ${{ env.ENVIRONMENT == 'prod' }}





2\. Secrets: conditions cannot be applied on secrets, as it is not a best practice. But, used for fetching the secrets from github UI.

Ex:

steps:

&#x20; - name: Setup SSH

&#x20;   uses: webfactory/ssh-agent@v0.7.0

&#x20;   with:

&#x20;     ssh-private-key: ${{ secrets.SSH\_PRIVATE\_KEY }}



3\. job status/step status (Most important): conditions applied on previous job/step status.

Ex:

if: ${{ job.status == 'success' }}

Job possible status:

success

failure

cancelled

skipped



job/step status usage in another way:



if: ${{ success() }}	==> executes the job/step, only if previous job/step is successful.

if: ${{ failure() }}	==> executes the job/step, only if previous job/step is failed.

if: ${{ failure() }}	==> executes the job/step every time, no care about the status of previous job/step.



step Ex:

steps:

&#x20; - name: Run tests

&#x20;   run: exit 1   # simulate failure



&#x20; - name: Run on failure

&#x20;   if: ${{ failure() }}

&#x20;   run: echo "Tests failed!"





job Ex:

cleanup:

&#x20; if: ${{ always() }}

&#x20; runs-on: ubuntu-latest



&#x20; steps:

&#x20;   - run: echo "Cleaning resources..."



job status is mostly used with another scenario, which is needs.



4\. needs: needs can also be combined with job status. needs usually defines the required job for executing the next job.

👉 ❌ needs CANNOT be used with steps

👉 ✅ needs works ONLY with jobs



Ex:

on: push



jobs:

&#x20; build:

&#x20;   runs-on: ubuntu-latest

&#x20;   steps:

&#x20;     - name: Print message

&#x20;       run: echo "Hello Madhav"



&#x20; notify:

&#x20;   needs: build

&#x20;   if: ${{ failure() }}

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - run: echo "Sending alert..."



You can even skip the status of previous job.



on: push



jobs:

&#x20; build:

&#x20;   runs-on: ubuntu-latest

&#x20;   steps:

&#x20;     - name: Print message

&#x20;       run: echo "Hello Madhav"



&#x20; notify:

&#x20;   needs: build

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - run: echo "Printing Message..."





👉 if: ${{ job.status == 'success' }}

❌ Not the best practice

👉 if: ${{ needs.build.result == 'success' }}

✅ best practice







5\. runner: you can fetch the data of runner and can also apply conditions based on the runner.



Ex:

runs-on: ubuntu-latest



jobs:

&#x20; build:

&#x20;   if: ${{ runner.os != 'Linux' }}

&#x20;   run: echo "running on ${{ runner.os}}"



6\. step output: Access previous step output.



Ex:

if: ${{ steps.build.outputs.version == 'prod' }}



7\. matrix strategy: matrix is a kind of strategy lets you run the same job multiple times with different configurations.

Ex:

if: ${{ matrix.node == 18 }}



8\. inputs:

👉 Used in reusable workflows / manual triggers

if: ${{ inputs.environment == 'prod' }}



9\. outputs: fetch the details and store them as outputs for reusing.



a. Simple step output:

👉 Goal: Generate a random number and use it later

jobs:

&#x20; example:

&#x20;   runs-on: ubuntu-latest

&#x20;   steps:

&#x20;     - name: Generate random number

&#x20;       id: random

&#x20;       run: echo "number=$RANDOM" >> $GITHUB\_OUTPUT



&#x20;     - name: Use the output

&#x20;       run: echo "Random number is ${{ steps.random.outputs.number }}"



b. passing output between jobs.

👉 Goal: Share a value from one job to another

jobs:

&#x20; job1:

&#x20;   runs-on: ubuntu-latest

&#x20;   outputs:

&#x20;     message: ${{ steps.setmsg.outputs.msg }}



&#x20;   steps:

&#x20;     - name: Set message

&#x20;       id: setmsg

&#x20;       run: echo "msg=Hello World" >> $GITHUB\_OUTPUT



&#x20; job2:

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: job1



&#x20;   steps:

&#x20;     - name: Print message

&#x20;       run: echo "${{ needs.job1.outputs.message }}"



c. Dynamic Environment Example:

👉 Goal: Decide environment dynamically

jobs:

&#x20; decide-env:

&#x20;   runs-on: ubuntu-latest

&#x20;   outputs:

&#x20;     env: ${{ steps.setenv.outputs.env }}



&#x20;   steps:

&#x20;     - id: setenv

&#x20;       run: |

&#x20;         if \[ "${{ github.ref }}" == "refs/heads/main" ]; then

&#x20;           echo "env=prod" >> $GITHUB\_OUTPUT

&#x20;         else

&#x20;           echo "env=dev" >> $GITHUB\_OUTPUT

&#x20;         fi



&#x20; use-env:

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: decide-env



&#x20;   steps:

&#x20;     - run: echo "Deploying to ${{ needs.decide-env.outputs.env }}"



d. passing multiple outputs:

👉 Goal: Send multiple values

jobs:

&#x20; producer:

&#x20;   runs-on: ubuntu-latest

&#x20;   outputs:

&#x20;     name: ${{ steps.data.outputs.name }}

&#x20;     age: ${{ steps.data.outputs.age }}



&#x20;   steps:

&#x20;     - id: data

&#x20;       run: |

&#x20;         echo "name=John" >> $GITHUB\_OUTPUT

&#x20;         echo "age=25" >> $GITHUB\_OUTPUT



&#x20; consumer:

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: producer



&#x20;   steps:

&#x20;     - run: |

&#x20;         echo "Name: ${{ needs.producer.outputs.name }}"

&#x20;         echo "Age: ${{ needs.producer.outputs.age }}"



e. using output in if condition:

👉 Goal: Control execution

jobs:

&#x20; check:

&#x20;   runs-on: ubuntu-latest

&#x20;   outputs:

&#x20;     run\_job: ${{ steps.check.outputs.run }}



&#x20;   steps:

&#x20;     - id: check

&#x20;       run: echo "run=true" >> $GITHUB\_OUTPUT



&#x20; conditional-job:

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: check

&#x20;   if: ${{ needs.check.outputs.run\_job == 'true' }}



&#x20;   steps:

&#x20;     - run: echo "This runs only if condition is true"



f. Output in the form of JSON (Advanced 🔥)

👉 Goal: Pass structured data

jobs:

&#x20; producer:

&#x20;   runs-on: ubuntu-latest

&#x20;   outputs:

&#x20;     data: ${{ steps.json.outputs.data }}



&#x20;   steps:

&#x20;     - id: json

&#x20;       run: |

&#x20;         echo 'data={"name":"Madhav","role":"DevOps"}' >> $GITHUB\_OUTPUT



&#x20; consumer:

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: producer



&#x20;   steps:

&#x20;     - run: |

&#x20;         echo "Full JSON: ${{ needs.producer.outputs.data }}"









convert Logic to YAML:

\--------------------------

Ex-1:

\------



🧠 Terraform Pipeline Logic (in Words)

🔹 1. Trigger Conditions



This pipeline is triggered when:



* Code is pushed to the main branch
* A pull request is created targeting main
* A release is published





🔹 2. CI Stage – Terraform Plan



For every trigger event:



* The pipeline runs a Terraform CI job
* It executes for three environments:

&#x09;dev, test, prod



However:

* During a pull request, the pipeline:

  * Runs only for dev and test
  * Skips prod (to avoid unnecessary or risky planning)



* CI Job Steps (for each environment):

  1. Checkout the repository code
  2. Install Terraform
  3. Configure AWS credentials dynamically based on environment
  4. Initialize Terraform
  5. Select the workspace:

     * If it exists → use it
     * If not → create it
  6. Validate Terraform configuration
  7. Generate a plan file
  8. Upload the plan as an artifact for later use





🔹 3. CD Stage – Deployment Flow



Deployment follows a sequential promotion pipeline:



dev → test → prod



Each stage depends on the success of the previous one.





🔹 4. Dev Deployment



The dev deployment runs only if:

* Event is push OR release



Steps:

1. Download dev plan artifact
2. Apply Terraform changes to dev environment





🔹 5. Test Deployment



The test deployment runs only if:

* Dev deployment succeeds
* Event is push OR release



Steps:

1. Download test plan artifact
2. Apply Terraform changes to test environment





🔹 6. Prod Deployment



The production deployment runs only if:

* Test deployment succeeds
* Event is release only (not push, not PR)



Steps:

1. Download prod plan artifact
2. Apply Terraform changes to production environment





🔥 Overall Flow Summary

1. Run Terraform plans for all environments (except prod on PR)
2. On push/release:

   * Deploy to dev
   * Then test
3. On release only:

   * Finally deploy to prod



🎯 Key Design Principles

✅ Environment isolation using workspaces

✅ Artifact reuse (plan → apply)

✅ Safe production deployment (only on release)

✅ Promotion-based deployment (dev → test → prod)

✅ Reduced risk in PRs (no prod execution)





🧩 One-liner (Interview Gold 🔥)



👉

“This pipeline first generates Terraform plans for all environments, skips production during pull requests, and then promotes deployments sequentially from dev to test and finally to production, where production is deployed only on release events.”





YAML:

\-------



name: Production Terraform Pipeline



on:

&#x20; push:

&#x20;   branches: \[main]

&#x20; pull\_request:

&#x20;   branches: \[main]

&#x20; release:

&#x20;   types: \[published]



jobs:

&#x20; terraform-ci:

&#x20;   name: Terraform CI (Plan)

&#x20;   runs-on: ubuntu-latest



&#x20;   strategy:

&#x20;     matrix:

&#x20;       env: \[dev, test, prod]



&#x20;   if: ${{ github.event\_name != 'pull\_request' || matrix.env != 'prod' }}



&#x20;   steps:

&#x20;     - name: Checkout code

&#x20;       uses: actions/checkout@v3



&#x20;     - name: Setup Terraform

&#x20;       uses: hashicorp/setup-terraform@v2



&#x20;     - name: Configure AWS Credentials

&#x20;       uses: aws-actions/configure-aws-credentials@v2

&#x20;       with:

&#x20;         aws-access-key-id: ${{ secrets\[format('AWS\_ACCESS\_KEY\_ID\_{0}', matrix.env)] }}

&#x20;         aws-secret-access-key: ${{ secrets\[format('AWS\_SECRET\_ACCESS\_KEY\_{0}', matrix.env)] }}

&#x20;         region: ap-south-1



&#x20;     - name: Terraform Init

&#x20;       run: terraform init



&#x20;     - name: Select Workspace

&#x20;       run: |

&#x20;         terraform workspace select ${{ matrix.env }} || terraform workspace new ${{ matrix.env }}



&#x20;     - name: Terraform Validate

&#x20;       run: terraform validate



&#x20;     - name: Terraform Plan

&#x20;       run: terraform plan -out=tfplan-${{ matrix.env }}



&#x20;     - name: Upload Plan Artifact

&#x20;       uses: actions/upload-artifact@v3

&#x20;       with:

&#x20;         name: tfplan-${{ matrix.env }}

&#x20;         path: tfplan-${{ matrix.env }}



&#x20; terraform-cd-dev:

&#x20;   name: Terraform CD (Dev)

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: terraform-ci

&#x20;   if: ${{ github.event\_name == 'push' || github.event\_name == 'release' }}



&#x20;   steps:

&#x20;     - name: Checkout code

&#x20;       uses: actions/checkout@v3



&#x20;     - name: Setup Terraform

&#x20;       uses: hashicorp/setup-terraform@v2



&#x20;     - name: Configure AWS Credentials

&#x20;       uses: aws-actions/configure-aws-credentials@v2

&#x20;       with:

&#x20;         aws-access-key-id: ${{ secrets.AWS\_ACCESS\_KEY\_ID\_dev }}

&#x20;         aws-secret-access-key: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY\_dev }}

&#x20;         region: ap-south-1



&#x20;     - name: Terraform Init

&#x20;       run: terraform init



&#x20;     - name: Select Workspace

&#x20;       run: terraform workspace select dev



&#x20;     - name: Download Plan Artifact

&#x20;       uses: actions/download-artifact@v3

&#x20;       with:

&#x20;         name: tfplan-dev



&#x20;     - name: Terraform Apply

&#x20;       run: terraform apply tfplan-dev



&#x20; terraform-cd-test:

&#x20;   name: Terraform CD (Test)

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: terraform-cd-dev

&#x20;   if: ${{ github.event\_name == 'push' || github.event\_name == 'release' }}



&#x20;   steps:

&#x20;     - name: Checkout code

&#x20;       uses: actions/checkout@v3



&#x20;     - name: Setup Terraform

&#x20;       uses: hashicorp/setup-terraform@v2



&#x20;     - name: Configure AWS Credentials

&#x20;       uses: aws-actions/configure-aws-credentials@v2

&#x20;       with:

&#x20;         aws-access-key-id: ${{ secrets.AWS\_ACCESS\_KEY\_ID\_test }}

&#x20;         aws-secret-access-key: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY\_test }}

&#x20;         region: ap-south-1



&#x20;     - name: Terraform Init

&#x20;       run: terraform init



&#x20;     - name: Select Workspace

&#x20;       run: terraform workspace select test



&#x20;     - name: Download Plan Artifact

&#x20;       uses: actions/download-artifact@v3

&#x20;       with:

&#x20;         name: tfplan-test



&#x20;     - name: Terraform Apply

&#x20;       run: terraform apply tfplan-test



&#x20; terraform-cd-prod:

&#x20;   name: Terraform CD (Prod)

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: terraform-cd-test

&#x20;   if: ${{ github.event\_name == 'release' }}



&#x20;   steps:

&#x20;     - name: Checkout code

&#x20;       uses: actions/checkout@v3



&#x20;     - name: Setup Terraform

&#x20;       uses: hashicorp/setup-terraform@v2



&#x20;     - name: Configure AWS Credentials

&#x20;       uses: aws-actions/configure-aws-credentials@v2

&#x20;       with:

&#x20;         aws-access-key-id: ${{ secrets.AWS\_ACCESS\_KEY\_ID\_prod }}

&#x20;         aws-secret-access-key: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY\_prod }}

&#x20;         region: ap-south-1



&#x20;     - name: Terraform Init

&#x20;       run: terraform init



&#x20;     - name: Select Workspace

&#x20;       run: terraform workspace select prod



&#x20;     - name: Download Plan Artifact

&#x20;       uses: actions/download-artifact@v3

&#x20;       with:

&#x20;         name: tfplan-prod



&#x20;     - name: Terraform Apply

&#x20;       run: terraform apply tfplan-prod









Tree structure:

\-----------------



Production Terraform Pipeline

│

├── on

│   ├── push

│   │   └── branches: \[main]

│   ├── pull\_request

│   │   └── branches: \[main]

│   └── release

│       └── types: \[published]

│

├── jobs

│   │

│   ├── terraform-ci (Plan)

│   │   ├── runs-on: ubuntu-latest

│   │   ├── strategy

│   │   │   └── matrix

│   │   │       └── env: \[dev, test, prod]

│   │   ├── if: (exclude prod on pull\_request)

│   │   └── steps

│   │       ├── Checkout code

│   │       ├── Setup Terraform

│   │       ├── Configure AWS Credentials (dynamic per env)

│   │       ├── Terraform Init

│   │       ├── Select Workspace (dev/test/prod)

│   │       ├── Terraform Validate

│   │       ├── Terraform Plan (tfplan-env)

│   │       └── Upload Plan Artifact

│   │

│   ├── terraform-cd-dev

│   │   ├── runs-on: ubuntu-latest

│   │   ├── needs: terraform-ci

│   │   ├── if: push OR release

│   │   └── steps

│   │       ├── Checkout code

│   │       ├── Setup Terraform

│   │       ├── Configure AWS Credentials (dev)

│   │       ├── Terraform Init

│   │       ├── Select Workspace (dev)

│   │       ├── Download Plan (tfplan-dev)

│   │       └── Terraform Apply

│   │

│   ├── terraform-cd-test

│   │   ├── runs-on: ubuntu-latest

│   │   ├── needs: terraform-cd-dev

│   │   ├── if: push OR release

│   │   └── steps

│   │       ├── Checkout code

│   │       ├── Setup Terraform

│   │       ├── Configure AWS Credentials (test)

│   │       ├── Terraform Init

│   │       ├── Select Workspace (test)

│   │       ├── Download Plan (tfplan-test)

│   │       └── Terraform Apply

│   │

│   └── terraform-cd-prod

│       ├── runs-on: ubuntu-latest

│       ├── needs: terraform-cd-test

│       ├── if: release only

│       └── steps

│           ├── Checkout code

│           ├── Setup Terraform

│           ├── Configure AWS Credentials (prod)

│           ├── Terraform Init

│           ├── Select Workspace (prod)

│           ├── Download Plan (tfplan-prod)

│           └── Terraform Apply

│

└── Flow

&#x20;   └── terraform-ci → terraform-cd-dev → terraform-cd-test → terraform-cd-prod















Ex-2:

🧠 Pipeline Logic – Deploy Nginx on AWS EC2

🔹 1. Trigger Condition



This pipeline runs when:

* Code is pushed to the main branch



🔹 2. Step 1: Provision Infrastructure (EC2 Creation)



Job: provision-infra-cli

This job is responsible for creating an EC2 instance using AWS CLI.



Steps:

1. Configure AWS credentials using stored GitHub secrets
2. Launch a new EC2 instance with:

   * AMI ID
   * Instance type (t2.micro)
   * Key pair
   * Security group
3. Wait until the EC2 instance is in running state
4. Fetch:

   * Instance ID
   * Public IP address
5. Store these values as outputs:

   * ec2\_id
   * ec2\_ip



👉 These outputs will be used by later jobs



🔹 3. Step 2: Configure EC2 (Install Nginx)

Job: ssh-into-ec2

This job depends on:

needs: provision-infra-cli

👉 Meaning it runs only after EC2 is successfully created



Steps:

1. Load SSH private key securely using GitHub Secrets
2. Wait for EC2 SSH readiness:

   * Try connecting multiple times (retry loop)
   * Ensures the instance is fully accessible
3. Connect to EC2 via SSH and:

   * Update package list
   * Install Nginx
   * Start Nginx service
   * Enable Nginx to start on boot



🔹 4. Step 3: Deploy Application

Job: deploy-app

This job depends on:

needs: ssh-into-ec2

👉 Meaning it runs only after Nginx is installed



Steps:

1. Setup SSH access again
2. Connect to EC2 and:

   * Remove default web files
   * Create a new HTML page:

     * Hello from CI/CD Pipeline
   * Place it in:

     * /var/www/html/index.html

👉 This becomes the homepage served by Nginx



🔹 5. Step 4: Verify Deployment

Job: deploy-verification

This job depends on:

needs: deploy-app

👉 Meaning it runs only after app deployment



Steps:

1. Send HTTP request using curl to:

   * http://<EC2\_PUBLIC\_IP>
2. Verify that:

   * Nginx is running
   * HTML page is accessible





🔥 Overall Flow

Provision EC2 → Configure EC2 → Deploy App → Verify Deployment





🎯 Key Concepts Used

✅ Infrastructure provisioning using AWS CLI

✅ Passing data between jobs using outputs

✅ Sequential execution using needs

✅ SSH-based remote configuration

✅ Retry mechanism for reliability

✅ End-to-end deployment validation





🧩 One-liner (Interview Gold 🔥)



👉

“This pipeline provisions an EC2 instance, configures it by installing Nginx over SSH, deploys a static web page, and finally verifies the deployment by accessing the application via its public IP.”





YAML:

\------



name: Deploy Nginx on AWS EC2



on:

&#x20; push:

&#x20;   branches: \[ "main" ]



jobs:

&#x20; provision-infra-cli:

&#x20;   name: Provision EC2 instance

&#x20;   runs-on: ubuntu-latest



&#x20;   outputs:

&#x20;     ec2\_ip: ${{ steps.ec2.outputs.ec2\_ip }}

&#x20;     ec2\_id: ${{ steps.ec2.outputs.ec2\_id }}



&#x20;   steps:

&#x20;     - name: Configure AWS credentials

&#x20;       uses: aws-actions/configure-aws-credentials@v2

&#x20;       with:

&#x20;         aws-access-key-id: ${{ secrets.AWS\_ACCESS\_KEY\_ID }}

&#x20;         aws-secret-access-key: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY }}

&#x20;         aws-region: us-east-1



&#x20;     - name: Create or Launch EC2

&#x20;       id: ec2

&#x20;       run: |

&#x20;         INSTANCE\_ID=$(aws ec2 run-instances \\

&#x20;           --image-id ami-0abcdef12345 \\

&#x20;           --instance-type t2.micro \\

&#x20;           --key-name my-key \\

&#x20;           --security-group-ids sg-123456 \\

&#x20;           --query 'Instances\[0].InstanceId' \\

&#x20;           --output text)



&#x20;         aws ec2 wait instance-running --instance-ids $INSTANCE\_ID



&#x20;         IP=$(aws ec2 describe-instances \\

&#x20;           --instance-ids $INSTANCE\_ID \\

&#x20;           --query 'Reservations\[0].Instances\[0].PublicIpAddress' \\

&#x20;           --output text)



&#x20;         echo "ec2\_ip=$IP" >> $GITHUB\_OUTPUT

&#x20;         echo "ec2\_id=$INSTANCE\_ID" >> $GITHUB\_OUTPUT



&#x20; ssh-into-ec2:

&#x20;   name: Configure EC2 (Install Nginx)

&#x20;   needs: provision-infra-cli

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - name: Setup SSH

&#x20;       uses: webfactory/ssh-agent@v0.7.0

&#x20;       with:

&#x20;         ssh-private-key: ${{ secrets.SSH\_PRIVATE\_KEY }}



&#x20;     - name: Wait for SSH readiness

&#x20;       run: |

&#x20;         for i in {1..10}; do

&#x20;           ssh -o StrictHostKeyChecking=no ubuntu@${{ needs.provision-infra-cli.outputs.ec2\_ip }} "echo SSH ready" \&\& break

&#x20;           echo "Waiting for SSH..."

&#x20;           sleep 10

&#x20;         done



&#x20;     - name: Install Nginx

&#x20;       run: |

&#x20;         ssh -o StrictHostKeyChecking=no ubuntu@${{ needs.provision-infra-cli.outputs.ec2\_ip }} << 'EOF'

&#x20;           set -e

&#x20;           sudo apt update

&#x20;           sudo apt install -y nginx

&#x20;           sudo systemctl start nginx

&#x20;           sudo systemctl enable nginx

&#x20;         EOF



&#x20; deploy-app:

&#x20;   name: Deploy Application

&#x20;   needs: ssh-into-ec2

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - name: Setup SSH

&#x20;       uses: webfactory/ssh-agent@v0.7.0

&#x20;       with:

&#x20;         ssh-private-key: ${{ secrets.SSH\_PRIVATE\_KEY }}



&#x20;     - name: Deploy HTML Page

&#x20;       run: |

&#x20;         ssh -o StrictHostKeyChecking=no ubuntu@${{ needs.provision-infra-cli.outputs.ec2\_ip }} << 'EOF'

&#x20;           set -e

&#x20;           sudo rm -rf /var/www/html/\*

&#x20;           echo "<h1>Hello from CI/CD Pipeline</h1>" | sudo tee /var/www/html/index.html

&#x20;         EOF



&#x20; deploy-verification:

&#x20;   name: Verify Deployment

&#x20;   needs: deploy-app

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;     - name: Verify Application

&#x20;       run: |

&#x20;         curl http://${{ needs.provision-infra-cli.outputs.ec2\_ip }}







Tree structure:

\---------------





root (map)

├── name (string)

│   └── Deploy Nginx on AWS EC2

│

├── on (map)

│   └── push (map)

│       └── branches (list)

│           └── \[0] → "main"

│

└── jobs (map)

&#x20;   ├── provision-infra-cli (object)

&#x20;   │   ├── runs-on → string

&#x20;   │   ├── outputs (map)

&#x20;   │   │   ├── ec2\_ip → string (expression)

&#x20;   │   │   └── ec2\_id → string (expression)

&#x20;   │   └── steps (list)

&#x20;   │       ├── \[0] Configure AWS (object)

&#x20;   │       └── \[1] Launch EC2 (object)

&#x20;   │

&#x20;   ├── ssh-into-ec2 (object)

&#x20;   │   ├── needs → string

&#x20;   │   ├── steps (list)

&#x20;   │       ├── \[0] Setup SSH

&#x20;   │       ├── \[1] Wait for SSH

&#x20;   │       └── \[2] Install Nginx

&#x20;   │

&#x20;   ├── deploy-app (object)

&#x20;   │   ├── needs → string

&#x20;   │   └── steps (list)

&#x20;   │       ├── \[0] Setup SSH

&#x20;   │       └── \[1] Deploy HTML

&#x20;   │

&#x20;   └── deploy-verification (object)

&#x20;       ├── needs → string

&#x20;       └── steps (list)

&#x20;           └── \[0] Curl Verification







🚀 Reusable Workflows (VERY POWERFUL):

\-----------------------------------------

👉 Instead of duplicating YAML in multiple repos

👉 You create one workflow → reuse everywhere



🧠 Why Needed?



❌ Without reusable workflows:



Copy-paste pipelines

Hard to maintain



✅ With reusable workflows:



Centralized logic

Reusable DevOps standards



💡 Real Use Case



👉 One Terraform pipeline

👉 Used across:

* dev
* staging
* prod



🧠 Matrix vs Reusable (Important)

| Feature   | Matrix                  | Reusable Workflow      |

| --------- | ----------------------- | ---------------------- |

| Purpose   | Parallel runs           | Reuse logic            |

| Use case  | Multiple configs        | Standard pipelines     |

| Execution | Same job multiple times | Calls another workflow |





Ex:

\-----



Reusable workflow (Terraform CI/CD) - YAML:

\----------------------------------------------

path where the YAML workflow will be stored:

📁.github/workflows/terraform-pipeline.yml



name: Reusable Terraform CI/CD Pipeline



on:

&#x20; workflow\_call:

&#x20;   inputs:

&#x20;     environment:

&#x20;       required: true

&#x20;       type: string

&#x20;     aws\_region:

&#x20;       required: true

&#x20;       type: string



jobs:



&#x20; terraform-ci:

&#x20;   name: Terraform CI

&#x20;   runs-on: ubuntu-latest



&#x20;   env:

&#x20;     AWS\_REGION: ${{ inputs.aws\_region }}

&#x20;     TF\_STATE\_BUCKET: ${{ secrets.TF\_STATE\_BUCKET }}



&#x20;   steps:

&#x20;     - name: Checkout code

&#x20;       uses: actions/checkout@v3



&#x20;     - name: Setup Terraform

&#x20;       uses: hashicorp/setup-terraform@v2



&#x20;     - name: Configure AWS Credentials

&#x20;       uses: aws-actions/configure-aws-credentials@v2

&#x20;       with:

&#x20;         aws-access-key-id: ${{ secrets.AWS\_ACCESS\_KEY\_ID }}

&#x20;         aws-secret-access-key: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY }}

&#x20;         region: ${{ env.AWS\_REGION }}



&#x20;     - name: Terraform Init

&#x20;       run: |

&#x20;         terraform init \\

&#x20;           -backend-config="bucket=${{ env.TF\_STATE\_BUCKET }}" \\

&#x20;           -backend-config="key=${{ inputs.environment }}-${{ env.AWS\_REGION }}.tfstate" \\

&#x20;           -backend-config="region=${{ env.AWS\_REGION }}"



&#x20;     - name: Select/Create Workspace

&#x20;       run: |

&#x20;         terraform workspace select ${{ inputs.environment }} || terraform workspace new ${{ inputs.environment }}



&#x20;     - name: Terraform Validate

&#x20;       run: terraform validate



&#x20;     - name: Terraform Plan

&#x20;       run: terraform plan -var="aws\_region=${{ env.AWS\_REGION }}" -out=tfplan



&#x20;     - name: Upload Plan Artifact

&#x20;       uses: actions/upload-artifact@v3

&#x20;       with:

&#x20;         name: tfplan-${{ inputs.environment }}

&#x20;         path: tfplan





&#x20; terraform-cd:

&#x20;   name: Terraform CD

&#x20;   runs-on: ubuntu-latest

&#x20;   needs: terraform-ci



&#x20;   environment: ${{ inputs.environment }}



&#x20;   env:

&#x20;     AWS\_REGION: ${{ inputs.aws\_region }}

&#x20;     TF\_STATE\_BUCKET: ${{ secrets.TF\_STATE\_BUCKET }}



&#x20;   steps:

&#x20;     - name: Checkout code

&#x20;       uses: actions/checkout@v3



&#x20;     - name: Setup Terraform

&#x20;       uses: hashicorp/setup-terraform@v2



&#x20;     - name: Configure AWS Credentials

&#x20;       uses: aws-actions/configure-aws-credentials@v2

&#x20;       with:

&#x20;         aws-access-key-id: ${{ secrets.AWS\_ACCESS\_KEY\_ID }}

&#x20;         aws-secret-access-key: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY }}

&#x20;         region: ${{ env.AWS\_REGION }}



&#x20;     - name: Terraform Init

&#x20;       run: |

&#x20;         terraform init \\

&#x20;           -backend-config="bucket=${{ env.TF\_STATE\_BUCKET }}" \\

&#x20;           -backend-config="key=${{ inputs.environment }}-${{ env.AWS\_REGION }}.tfstate" \\

&#x20;           -backend-config="region=${{ env.AWS\_REGION }}"



&#x20;     - name: Select/Create Workspace

&#x20;       run: |

&#x20;         terraform workspace select ${{ inputs.environment }} || terraform workspace new ${{ inputs.environment }}



&#x20;     - name: Download Plan Artifact

&#x20;       uses: actions/download-artifact@v3

&#x20;       with:

&#x20;         name: tfplan-${{ inputs.environment }}



&#x20;     - name: Terraform Apply

&#x20;       run: terraform apply -auto-approve tfplan







Main workflow:

\---------------

path where the YAML workflow will be stored:

📁 .github/workflows/main.yml



name: Terraform Multi-Env Multi-Region Pipeline



on:

&#x20; push:

&#x20;   branches:

&#x20;     - main



jobs:



&#x20; # 🔹 DEV (parallel across regions)

&#x20; deploy-dev:

&#x20;   name: Deploy Dev

&#x20;   strategy:

&#x20;     matrix:

&#x20;       region: \[ap-south-1, us-west-1]



&#x20;   uses: ./.github/workflows/terraform-pipeline.yml

&#x20;   with:

&#x20;     environment: dev

&#x20;     aws\_region: ${{ matrix.region }}



&#x20; # 🔹 QA (wait for ALL dev jobs)

&#x20; deploy-qa:

&#x20;   name: Deploy QA

&#x20;   needs: deploy-dev

&#x20;   strategy:

&#x20;     matrix:

&#x20;       region: \[ap-south-1, us-west-1]



&#x20;   uses: ./.github/workflows/terraform-pipeline.yml

&#x20;   with:

&#x20;     environment: qa

&#x20;     aws\_region: ${{ matrix.region }}



&#x20; # 🔹 PROD (wait for ALL QA jobs)

&#x20; deploy-prod:

&#x20;   name: Deploy Prod

&#x20;   needs: deploy-qa

&#x20;   strategy:

&#x20;     matrix:

&#x20;       region: \[ap-south-1, us-west-1]



&#x20;   uses: ./.github/workflows/terraform-pipeline.yml

&#x20;   with:

&#x20;     environment: prod

&#x20;     aws\_region: ${{ matrix.region }}



&#x20;   environment:

&#x20;     name: production   # manual approval







🧠 What This Achieves



🔹 Parallel Regions



dev:

&#x20; ap-south-1   → runs

&#x20; us-west-1    → runs (parallel)



qa: (wait for dev completion and qa starts with dev)

&#x20; ap-south-1   → runs

&#x20; us-west-1    → runs (parallel)



prod: (wait for dqa completion and prod starts with qa after manual approval)

&#x20; ap-south-1   → runs

&#x20; us-west-1    → runs (parallel)



🔹 Controlled Promotion



✔ QA starts only after ALL dev jobs succeed

✔ Prod starts only after ALL QA jobs succeed





🔹 Sequential Environments



dev (all regions)

&#x20;  ↓

qa (all regions)

&#x20;  ↓

prod (all regions)



🧠 End-to-End Flow (Visual Tree)

push → main

&#x20;  │

&#x20;  ▼

deploy-dev (in all regions)

&#x20;  │

&#x20;  ▼

(terraform-pipeline.yml)

&#x20;  ├── terraform-ci

&#x20;  └── terraform-cd

&#x20;  │

&#x20;  ▼

deploy-qa (in all regions)

&#x20;  │

&#x20;  ▼

(terraform-pipeline.yml)

&#x20;  ├── terraform-ci

&#x20;  └── terraform-cd

&#x20;  │

&#x20;  ▼

deploy-prod (in all regions)

&#x20;  │

&#x20;  ▼

(manual approval)

&#x20;  │

&#x20;  ▼

(terraform-pipeline.yml)

&#x20;  ├── terraform-ci

&#x20;  └── terraform-cd







🧠 Why This Design is Powerful

🔹 1. Clean Separation



✔ CI and CD are separate jobs

✔ But still in one reusable workflow



🔹 2. Promotion Flow

dev → qa → prod



✔ Controlled using needs



🔹 3. Reusability



✔ Same pipeline reused for all environments

✔ Only inputs change



🔹 4. Safety



✔ Plan → reviewed

✔ Same plan → applied

✔ Prod → manual approval



🔹 5. Multi-Region Ready



✔ Passed via input

✔ Fully dynamic



🧠 Final Architecture



Main Workflow

&#x20;  ↓

Calls Reusable Workflow (per env)

&#x20;  ↓

Inside Reusable:

&#x20;  Job 1 → CI (init + validate + plan)

&#x20;  Job 2 → CD (apply) → depends on CI





Note in Reusable Workflow Example:



* Add AWS credentials like access\_key and secret\_key along with the existing bucket-name in your secrets manager of GitHub.
* Answer for a question being arised in my mind.

  * Ques: I've configured my S3 backend in the terraform config file, And again done here in CI/Cd reusable workflow, why is it so? Does it allow to do so? What happens if we do in such a way?
  * Answer: Yes, Terraform allows backend configuration both in code and during initialization using -backend-config. The CLI-provided values override the configuration defined in the code. In real-world CI/CD pipelines, it is a best practice to keep the backend block minimal in the Terraform code and dynamically pass environment-specific values like state file key and region during initialization.
  * This approach improves clarity, avoids accidental conflicts, and supports multi-region deployments more effectively.
  * So, I wish to use the same backend config without much changes in both terraform code and as well as CI/CD pipeline.



&#x20;







🚀 Resume-Level Upgrade



Designed a modular Terraform CI/CD pipeline using GitHub Actions with a reusable workflow containing separate CI and CD jobs, enabling environment-wise promotion flow, artifact-based plan reuse, multi-region deployments, and secure production releases with approval gates and secret handling.





