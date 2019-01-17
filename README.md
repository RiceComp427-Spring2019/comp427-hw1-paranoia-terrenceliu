# <img src="http://www.rice.edu/_images/rice-logo.jpg" width=180> Comp427, Spring 2018, Homework 1
## Rational Paranoia
The homework specifications, as well as the corresponding course slide decks,
can be found on the [Comp427 Piazza](https://piazza.com/class/jqifhp864b37ju).
This assignment is due **Thursday, January 17 at 6 p.m.**

You will do this homework by editing the _README.md_ file. It's in
[MarkDown format](https://guides.github.com/features/mastering-markdown/)
and will be rendered to beautiful HTML when you visit your GitHub repo.

## Student Information
Please also edit _README.md_ and replace your instructor's name and NetID with your own:

_Student name_: Terrence Liu

_Student NetID_: yl124

Your NetID is typically your initials and a numeric digit. That's
what we need here.

_If you contacted us in advance and we approved a late submission,
please cut-and-paste the text from that email here._

## Problem 1
- Scenario: TSA
- Assumptions:
  - Assume that I am the head of TSA in IAH. The number of passengers that go in and out of the airport everyday could be quite large.
- Assets:
  - Passenger
    - The safety of the passenger is the top most priority if I was the head of TSA.
  - Plane
    - We also need to make sure of the planes are free from attacks. If the plane went down during the flight, the safety of personnel could be endangered.
  - Airport 
    - We need to keep the order of the airport. If the airport shuts down, there could be quite a lot of consequences.
- Threats:
  - There could be terrorists trying to sneak pass the security check and commit attacks.
  - Some items or foods could potentially carry fatal viruses or germs. We definitely don't want those items be carried on into the airport or the planes.
- Countermeasures:
  - Set up security check before the passenger enters the main building. During the security check, the staff should scan the passenger's personal belonging to look for if there are anything suspicious. The staff should also scan the passenger's body to make sure they don't sneak in stuff inside their clothes or body.
  - Set up patrol stations with police dogs to regularly scan through the airport. The dogs could sniff the smell of dangerous liquid (e.g. nitroglycerin). 

## Problem 2
- Scenario: Grading
- Assumptions:
  - Assume it's a Computer Science class, where most of the homework are coding projects. 
  - Assume that we are using Github to download / submit codes, Canvas to enter grades.
- Assets:
  - Codes. Only the graders and the student that owns the repository could have access to that repository. No other students could have access to that repostiroy.
  - Grades. Only the graders have the access to create / update the grades. The students only have the right to read the grades. 

- Threats:
  - Plagirism. Students could potentially try to gain access to other  student's codes and copy their codes.
  - Cheating. Students may try to tamper with the timing system to submig their assignments after the deadline.
  - Steal identity. Students may try to steal the admin accounts and log into the system to change the grades. For example, steal the identity of TA and log into the Canvas as the instructor.
- Countermeasures:
  - We need to configure the permissions to the repository properly for the class. The repository must be private. I think there must be some automated tools that generates the repository and configure the access permissions.
  - To protect the instructor accounts, we can set up two-factor authentication whenever the instructor accounts being logged in. We assume that the mobile phone of the instructor is secure. Only the owner of the phone can unlock the phone with the technology such as FaceID. We only allow logging in if the request has been approved on the instructor's phone. 
  - To protect the integrity of the submission, we could have a centralized clocking system that whenever there is a push, we add a timestamp according to the centralized clocking system instaed of student's local time.
  - To prevent plagirism, we could utilize the existing algorithms that check if two pieces of codes have high similarity. We need to check very pair of the submissions to see if they are similar. Therefore it requires `O(n^2)` time to check the entire submission pools. It may be costly, however it's worth it.

## Problem 3
- Scenario: I'm a backend developer that is responsible to develop a login module that handles the user login/logout
- Assumptions:
  - Assume the frontend and the backend communicate over HTTP.
- Assets:
  - User login informations, including user name, user email, user passwords, etc.
  - The integraity of the database. I need to make sure the safety of the databse from attacks.
- Threats:
  - Leak of user information during transfering the data between the client and the server. 
  - Databse attacks. For example, there could be mallicious request that may commit injection attacks.
- Countermeasures:
  - We enforce HTTPS between the client and the server to encrypt the data transtered in between. Therefore, we could prevent the man in the middle to steal the informations when transfering the packets.
  - We use RESTful API for the endpoints of the server. After receiving the request, we validate the parameters to check if they are save to put into the databse. Some sort of injection attack checking could be performed here.
  - Don't save the password explicitly in the database. Instead, we hased the password and put it into the database. In this case, even if the database is compromised, the true password won't be leaked and therefore minimize the damage.
  - Enforce the authorization. If a request needs to perform some priviledge actions, for example, delete / update the accounts, it should obtain the proper authorization first then could proceeed. We could issue tokens to the authorized client and set limited expiration time, for example, 60 seconds.
