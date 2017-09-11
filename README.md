Simple REST service to manage user and group (ldap backend) using Python and Flask-RESTful library

## API

```
Group
- create : POST /groups
- delete (must be empty) : DELETE /groups/<groupdId>
- list groups : GET /groups
- group info : GET /groups/<groupId>
- add user to a group : POST /groups/<groupId>/users/<userId>
- remove user from a group : DELETE /groups/<groupId>/users/<userId>
- list user from a group : GET /groups/<groupId>/users


User
- search all ldap users (ldap filter): Get /ldapusers?filter=(uid=snsak*)
- get all users that belong to a least one group: GET /users
- get user information (key: uid) : GET /users/<userId>
- list group that the user belong to : GET /users/<userId>/groups


Auth:
- /login (return a session token)
- /logout
```

## How to start the backend server
- Install python and pip (python package manager)
- Install virtual env
```
pip install virtualenv
```
- clone the repo
```
git clone https://github.com/maduma/user-and-group.git
```
- Create a new python environment and install the requirement
```
virtualenv venv
source venv/bin/activate
pip install -r user-and-group/requirement.txt
```
- start the server
```
cd user-and-group
python api.py
```

