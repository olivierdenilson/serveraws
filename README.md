<b>Server AWS</b>

Códigos Server Amazon

Softwares Utilizados Filezilla para acesso FTP http://www.heidisql.com/ para acesso ao banco de dados Mysql <b> Putty Puttygen Plink <b>

<h2>Baixar Atualização Ubuntu Linux</h2>

sudo apt-get update


#Instalar Atualização Ubuntu Linux sudo apt-get upgrade

Instalação do Apache2
sudo apt-get install apache2

Instalação do PHP5
sudo apt-get install php5 php5-cli php5-dev php5-mcrypt php5-curl php5-gd libapache2-mod-php5

Istalação do Mysql e PHP My Admin
sudo apt-get install mysql-client mysql-server php5-mysql phpmyadmin

PERMISSÃO DE PASTA
chmod 755 -R /var/www/ chown ubuntu:ubuntu -R /var/www/

Configuração para criar varios sites que é direcionado para cada pasta.
#Simulação para dominio1.com.br

<VirtualHost *:80> ServerAdmin contato@dominio1.com.br ServerName dominio1.com.br ServerAlias *.dominio1.com.br

    # Indexes + Directory Root.
    DirectoryIndex index.html index.php
    DocumentRoot /var/www/wordpress/

    <Directory /var/www/wordpress/ >
        Options Indexes FollowSymLinks MultiViews
        AllowOverride all
        Order allow,deny
        allow from all
    </Directory>
    
   # CGI Directory
    ScriptAlias /cgi-bin/ /var/www/wordpress/cgi-bin/
    <Location /cgi-bin>
         Options +ExecCGI
    </Location>

    #Logfiles
    #ErrorLog  /var/www/wordpress/logs/error.log
    #CustomLog /var/www/wordpress/logs/access.log combined
#Simulação para dominio2.com.br

<VirtualHost *:80> ServerAdmin contato@dominio2.com.br ServerName dominio2.com.br ServerAlias *.dominio2.com.br

    # Indexes + Directory Root.
    DirectoryIndex index.html index.php
    DocumentRoot /var/www/dominio2/

    <Directory /var/www/dominio2/ >
        Options Indexes FollowSymLinks MultiViews
        AllowOverride all
        Order allow,deny
        allow from all
    </Directory>
    
   # CGI Directory
    ScriptAlias /cgi-bin/ /var/www/dominio2/cgi-bin/
    <Location /cgi-bin>
         Options +ExecCGI
    </Location>

    #Logfiles
    #ErrorLog  /var/www/dominio2/logs/error.log
    #CustomLog /var/www/dominio2/logs/access.log combined
