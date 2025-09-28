# django-HelloWorld
just some first steps in django, nothing for prod
Testing some stuff with a example project ("Build Progressive Web Apps: Python Django PWA Masterclass") from udemy.. let's see how it works.

# Creds (just localhost stuff)
Superadmin: luk:moo
Link: http://localhost:9000/admin/login/
mysql:3306 root:moo

# Start here from scratch

## Python
Python v3.12+ should be already there

## MySQL with brew
Install mysql using brew on macos (just if needed), maybe sqlite will do the job?
```Terminal
brew install mysql
unset TMPDIR
mysql_install_db --verbose --user=`whoami` --basedir="$(brew --prefix mysql)" --datadir=/usr/local/var/mysql --tmpdir=/tmp
mysql.server start
mysql_secure_installation
mysql.server status
brew install pkg-config
```

### Config
Configure mysql, create the db
```Terminal
mysql -u luk -p
show databases;
create database ft_pwa_db;
```

## Create venv
```Terminal
python3 -m venv venv
source venv/bin/activate
```

## Use pip in the venv to install some libs
```Terminal
pip install django django-pwa django-crispy-forms crispy-bootstrap5
pip install --upgrade pip
pip install pillow
pip install mysqlclient
```

## Start the project
Mind the dot after mysite to avoid subdirectory
Superuser needs -> username, mail, pwd, pwd
```Terminal
django-admin startproject mysite .
python manage.py startapp app
python manage.py migrate
python manage.py createsuperuser
```

# Run the Server
```Terminal
python manage.py runserver localhost:9000
```

# Migrations
```Terminal
python manage.py makemigrations
python manage.py migrate 
```
