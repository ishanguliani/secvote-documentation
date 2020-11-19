# Project brief
It is critical that online voting systems provide at least three basic security promises. Firstly, only registered and authorized citizens must be able to vote. Secondly, every voter must be able to cast exactly one vote, and finally, the voter's information must stay confidential. In this project, we propose SecVote - an end to end secure online voting system implemented as a web application that guarantees these three security promises. Under the hood, SecVote stores information as small chunks of data distributed across multiple machines - each of which uses SHA256 based end-to-end encryption in the database layer, application layer, and rest APIs to ensure data confidentiality and software security.

 By using secure communication channels and keeping data distributed we ensure that voting information cannot be read or changed by attackers while en-route or when at rest. Secure storage that uses hashing algorithms with salting ensures that passwords cannot be reverse engineered in case of a database breach.


# Demo

## One Candidate added
![Screen Shot 2020-10-29 at 4 57 25 PM](https://user-images.githubusercontent.com/8524069/97632575-14261500-1a09-11eb-9d4e-f3f73477005c.png)

## One Election added
![Screen Shot 2020-10-29 at 4 57 30 PM](https://user-images.githubusercontent.com/8524069/97632576-14261500-1a09-11eb-9338-ea21bbc10d6c.png)

# Screenshots

## Successful vote casting
![Screen Shot 2020-10-29 at 4 55 19 PM](https://user-images.githubusercontent.com/8524069/97632572-138d7e80-1a09-11eb-863f-ab6a4e2346e4.png)

## Vote added to Ballot box
![Screen Shot 2020-10-29 at 4 55 49 PM](https://user-images.githubusercontent.com/8524069/97632574-14261500-1a09-11eb-86fb-76c31dfe1d7c.png)

## Voting History Updated
![Screen Shot 2020-10-29 at 5 08 07 PM](https://user-images.githubusercontent.com/8524069/97632747-58191a00-1a09-11eb-9064-d59b0d8203be.png)

## Election Person Table Updated
![Screen Shot 2020-10-29 at 5 08 40 PM](https://user-images.githubusercontent.com/8524069/97632800-6d8e4400-1a09-11eb-807b-2392bb1b8cd1.png)

## Same voter cannot vote again
![Screen Shot 2020-10-29 at 4 55 41 PM](https://user-images.githubusercontent.com/8524069/97632573-138d7e80-1a09-11eb-9a21-455654ec7563.png)

# Running the Django Application

## Set up Django
1. Install python3.7+
2. Install django `pip3 install django` or `pip install django`
3. Navigate to the `secvote` folder
4. Run `$ python3 manage.py runserver` 

The server should now be up and running on localhost:8000 and we are ready to cast votes using the python program provided (see below). 

Please feel free to reach out to us in case the server set up fails. 

# Running the Testing Script
To make testing easier, we wrote a python program that reads information about the voter from given json files and takes an action accordingly. For instance you will find a json file `register.py` which will require you to register yourself as a voter. It looks like the following:
![Screen Shot 2020-10-29 at 5 24 57 PM](https://user-images.githubusercontent.com/8524069/97634275-ceb71700-1a0b-11eb-89c0-6b4f23a8da53.png)

1. Navigate to the `testing` dir from the root of the project directory.
2. Run `python3 program.py [JSON FILE]`. The information can be changed in each JSON file.
   1. `register.json`: Will register a new user.
   2. `login.json`: Will log a user in.
   3. `elections.json`: Will give all the open elections.
   4. `candidates.json`: Will give all the candidates that user can vote for.
   5. `cast.json`: Will cast a vote.
   6. `votinghistory.json`: Will give the user's voting history
   7. `result.json` : Will give the result of the election.
   
   
Once the vote is casted, you can further access the information as an administrator and look at the ballot box by visiting:
`localhost:8000/admin` with 
username: `mambas` 
password: `mambascsci655`

   
 # Future Work
In future, we plan to implement federated identity management with short-lived tokens where access to each resource is granted for a limited time on as-needed basis at each level.  Additionally, we would like to set up continuous deployment and testing pipelines which automatically detect and correct problems in the system.
