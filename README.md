Simple REST service to manage user and group (ldap backend) using Python and Flask-RESTful library

## API

```
Group
- create : PUT /groups/<groupId> *
- delete (must be empty) : DELETE /groups/<groupdId> *
- list groups : GET /groups
- group info : GET /groups/<groupId>
- add user to a group : PUT /groups/<groupId>/users/<userId> *
- remove user from a group : DELETE /groups/<groupId>/users/<userId> *
- list user from a group : GET /groups/<groupId>/users


User
- search all ldap users: Get /ldapusers?filter=<username substring> *
- get all users that belong to a least one group: GET /users
- get user information (key: uid) : GET /users/<userId>
- list group that the user belong to : GET /users/<userId>/groups


Auth:
- /login (return a session token) : POST (username, password)
- /logout : GET *

* add the Header "X-Auth-Token: <token-id>" to authenticate
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
sudo apt-get install libsasl2-dev python-dev libldap2-dev libssl-dev
virtualenv venv
source venv/bin/activate
pip install -r user-and-group/requirement.txt
```
- start the server
```
cd user-and-group
python api.py
```

- install local openldap for test
```
sudo apt install slapd ldap-utils
sudo service slapd start
```

- run unit tests suite
```
python test.py
```
