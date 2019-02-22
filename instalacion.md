#install odoo 12

# Install the PostgreSQL database
$ sudo apt updatehttp://localhost:8069/web/database/selector
$ sudo apt install postgresql postgresql-contrib
$ psql -V

$ ls /etc/postgresql/10/main
$ service  postgresql
$ service  postgresql status

$ sudo su  postgres (default username when you install postgres)
$ psql
- \l
- \du (lista de privilegios para el usuario)

-DROP DATABASE name;
-DROP USER name;

-CREATE USER rob10 WITH PASSWORD '12345';
-ALTER USER rob10 WITH SUPERUSER;
-CREATE DATABASE odoodb;


$ sudo su - postgres -c "createuser rob"
$ sudo su - postgres -c "createdb robdb"
$ sudo -u   postgres psql
# and run ..https://segmentfault.com/a/1190000013472741
grant all privileges on database robdb to rob;


# Install the Odoo system dependencies
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install git  # Install Git
$ sudo apt install python3-dev python3-pip # Python 3 for dev
$ sudo apt install build-essential libxslt-dev libzip-dev libldap2-dev libsasl2-dev libssl-dev


# Install less CSS preprocessor, 
$ wget -qO- https://deb.nodesource.com/setup_10.x | sudo -E bash -
$ sudo apt-get install -y nodejs
$ sudo npm install -g less less-plugin-clean-css 

# Install Odoo from source
$ git clone https://github.com/odoo/odoo.git -b 12.0 --depth=1 
#in to the virtualenv
$ pip3 install -r ~/odoo-dev/odoo/requirements.txt 
$ pip3 install num2words phonenumbers psycopg2-binary watchdog xlwt



# run odoo
$ ./odoo-bin --addons-path=addons --db-filter=^robdb$ -d robdb -i base

$ python3 odoo-bin --addons-path=addons start -d robdb -i base

#where i found the link of my database
localhost:8069/web/login?db=robdb
mail acount : admin
password : admin


#Tarea por hacer
sudo su -c "createuser -s $USER" baseData

-eliminamos el proyecto
-vamos a eliminar todas las bases de datos en postgres
-solo dejamos el username rob
-Ejecutamos  el siguiente script
-$ ./odoo-bin --addons-path=addons -i base
-esperemos que nos redireccione para crear una base de  datos
-cuando se procesen los datos(resetee el  formulario) 
reseteamos la apliacacion ya con las credenciales de la nueva base de  datos




