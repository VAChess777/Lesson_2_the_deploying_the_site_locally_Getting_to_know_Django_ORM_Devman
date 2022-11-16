# The project "Deploying the site locally" 

- The program can be deployed locally on your computer and connected to a database with employee visits.
- The program displays information on the "security panel" about active employee passes.
- The program displays information about the employee's time in the place of interest to us.
- The program displays information about employees who are currently in the place of interest to us.

### Software environment and installation:

Python3 should already be installed.

### Program installation:

Download the code: [https://github.com/VAChess777/Lesson_2_the_deploying_the_site_locally_Getting_to_know_Django_ORM_Devman](https://github.com/VAChess777/Lesson_2_the_deploying_the_site_locally_Getting_to_know_Django_ORM_Devman), or clone the `git` repository to a local folder:
```
https://github.com/VAChess777/Lesson_2_the_deploying_the_site_locally_Getting_to_know_Django_ORM_Devman
```

### Installing dependencies:
 
Use `pip` (or `pip3`, if there is a conflict with Python2) to install dependencies:
```bach
pip install -r requirements.txt
```

### About environment variables:

The program `settings.py ` there are environment variables in the `project` folder that are responsible for configuring access to the database.
create a `.env` file, place it in the root directory of the program. Put the following data in the `.env` file in the `key=value` format.

`HOST=` - web address of the Database connection point, for example `site.domain.ru`.                                             
`PORT=` - Database server port, for example `1234`.                                                                                                                          
`NAME=` - Database name.                                                       
`USER=` - Database user name.                                                                                                                                                           
`PASSWORD=` - Database user password.                 
`SECRET_KEY=` - Django secret key.              
`DEBUG=` - True for enabling debugging mode, False for production.

### How to run the program:

The security console is launched by the python command: `$ python manage.py runserver <server_address>:<port>`, where:
`<server_address>` - the address where the site server will be available.
`<port>` - the port on which the connection will be made.

Example of commands to run the program:

```bach
python manage.py runserver
python manage.py runserver localhost:80
python manage.py runserver 0.0.0.0:8000
python manage.py runserver 127.0.0.1:80
python manage.py runserver 127.0.0.1:8000
```

Log in to your browser at [127.0.0.1:8000](http://127.0.0.1:8000), and you will see the information of the 'security console.'

### How the program works:

The program consists of 7 script:

```manage.py``` - the main program that runs the script.   
```active_passcards_view.py``` - the program is located in the datacenter folder. The program shows how many active passes are available.                                             
```storage_information_view.py``` - the program is located in the datacenter folder. The program shows information about employees who are in the vault, and how long they are there.                           
```passcard_info_view.py``` - the program is located in the datacenter folder. The program calculates information about how many visits to the repository the employee of interest had, and was this visit suspicious.   
```settings.py``` - the program is located in the project folder. Responsible for setting up access to the employee database.   
```models.py``` - the program is located in the datacenter folder. The program is responsible for data models and their fields
```urls.py``` - the program is located in the project folder. Responsible for setting up links to the 'security console' pages
            
### Features works of the program:

The `active_passcards_view.py` program contains the functions:

* The `active_passcards_view` function - get active employee passes from the database.

The `storage_information_view.py` program contains the functions:

* The `storage_information_view` function - calculates information about how many visits to the repository the employee of interest had, and was this visit suspicious.
* The `get_duration` function - gets the difference between the start of the visit and the time when the employee left the object.
* The `format_duartion` function - formats the information received from the function `get_duration`.

The `passcard_info_view.py` program contains the functions:

* The `passcard_info_view` function - receives information about the visits of each employee. Calculates whether this visit was suspicious.
* The `get_object_or_404` function - checks the correctness of the entered passcard number.
* The `is_visit_long` function - compares the employee's stay time with the time we are interested in visiting the object.

### Project Goals

This code was written for educational purposes as part of an online course for web developers at [dvmn.org](https://dvmn.org/).