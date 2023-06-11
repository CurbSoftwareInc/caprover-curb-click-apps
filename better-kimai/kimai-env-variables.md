## Kimai Env Variables in yaml file

ADMINMAIL: $$cap_kimai-adminmail

ADMINPASS: $$cap_kimai-adminpass

MAILER_URL: $$cap_kimai-mailerurl

MAILER_FROM: $$cap_kimai-mailerfrom

DATABASE_URL: mysql://$$cap_mariadb-user:$$cap_mariadb-pass@srv-captain--$$cap_appname-db/$$cap_mariadb-db

TRUSTED_HOSTS: $$cap_appname.$$cap_root_domain,nginx,localhost,127.0.0.1

      
## Kimai Env Variables in CapRover Config

ADMINMAIL=admin@example.com

ADMINPASS=<your super secret password>
  
MAILER_URL=smtps://<smtp username>:<smtp password>@mail.example.com:<smtp port>
  
MAILER_FROM=no-reply@example.com
  
DATABASE_URL=mysql://kimaiuser:<password here>@<application at srv-captain--<db app name i.e. kimai-db/<db user i.e. kimai>
  
TRUSTED_HOSTS=kimai.<captains root domain>.com,nginx,localhost,127.0.0.1
