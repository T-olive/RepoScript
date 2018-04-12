#!/bin/bash
   echo "Installing dependencies..." 
   apt-get update
   apt-get install build-essential && apt-get install libreadline-dev && apt-get install libssl-dev && apt-get install  libpq5 && apt-get install libpq-dev && apt-get install libreadline5 && apt-get install libsqlite3-dev && apt-get install libpcap-dev && apt-get install openjdk-7-jre && apt-get install subversion && apt-get install git-core && apt-get install autoconf && apt-get install postgresql && apt-get install pgadmin3 && apt-get install curl && apt-get install zlib1g-dev && apt-get install libxml2-dev && apt-get install libxslt1-dev && apt-get install vncviewer && apt-get install libyaml-dev && apt-get install ruby1.9.3 && apt-get install nmap -y && gem install && apt-get install --verbose && apt-get install --debug && apt-get install pcaprub && apt-get install wirble && apt-get install pg && apt-get install sqlite3 && apt-get install msgpack && apt-get install activerecord && apt-get install redcarpet && apt-get install rspec && apt-get install simplecov && apt-get install yard && apt-get install bundler 
   echo "Clonning Metasploit..."  
   cd /opt 
   git clone https://github.com/rapid7/metasploit-framework.git 
   cd metasploit-framework bash -c 'for MSF in $(ls msf*); do ln -s /opt/metasploit-framework/$MSF /usr/local/bin/$MSF;done' 
   bundle install 

   su postgres 
   createuser msf -P -S -R -D 
   createdb -O msf msf 
   exit
   echo "production:" >> /opt/metasploit-framework/database.yml 
   echo "adapter: postgresql" >> /opt/metasploit-framework/database.yml 
   echo "database: msf" >> /opt/metasploit-framework/database.yml 
   echo "username: msf" >> /opt/metasploit-framework/database.yml 
   echo "password:" >> /opt/metasploit-framework/database.yml 
   echo "host: 127.0.0.1" >> /opt/metasploit-framework/database.yml 
   echo "port: 5432" >> /opt/metasploit-framework/database.yml 
   echo "pool: 75" >> /opt/metasploit-framework/database.yml 
   echo "timeout: 5" >> /opt/metasploit-framework/database.yml 
   sh -c "echo export MSF_DATABASE_CONFIG=/opt/metasploit-framework/database.yml >> ~/.bashrc" 

   msfconsole # open msf console and connect to db msf> db_connect -y 
   /opt/local/config/database.yml msf>
   exit

   msfrpcd -U msfuser2 -P msfpassword2 -S -a 127.0.0.1 -t Msg

if whiptail --title "Metasploit" --yesno "Conclusao da instalacao. Escolha yes para terminar" --fb 10 50
then
   echo "Aguarde"
   sleep 4
   echo "Execute => 'msfconsole'"
else
   echo "Interrompendo..."
   sleep 2
   echo "Operacao cancelada"
fi
