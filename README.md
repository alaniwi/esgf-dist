ESGF war file installation instructions
=========

Example instructions for esgf-web-fe version 2.5.0

o Stop the ESGF node:

sudo -s
esg-node stop

o Backup the current distribution:

cd /usr/local/tomcat/webapps/
cp -R esgf-web-fe ~/esgf-web-fe.backup
rm -rf esgf-web-fe

o Cleanup the Tomcat working directory:

cd /usr/local/tomcat/work/Catalina/localhost/
rm -rf esgf-web-fe/

o Clone the full GitHub repo containing the distribution files:

cd ~
git clone git@github.com:ESGF/esgf-dist.git

o Copy the desired distribution to a new location and unpack it:

cp esgf-dist/esgf-web-fe/esgf-web-fe.2.5.0.tar.gz /tmp/.
cd /tmp
tar xvfz esgf-web-fe.2.5.0.tar.gz

o Install the new distribution into Tomcat:

cp esgf-web-fe.2.5.0/esgf-web-fe.war /usr/local/tomcat/webapps/.

o Restart the ESGF node:

esg-node start

The war file will be unpacked automatically upon Tomcat restart.
