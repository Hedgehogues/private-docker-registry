# docker-registry
This is docker-image for private docker-registry

# Start

    docker-compose up

# Password

If you want to set password for your registry, you need set into docker-compose path to volumes:

    - $HOME/.credentionals:/auth
    
You need to use htpassword. 

1. First make sure you have the passlib module installed (note that passlib>=1.6 is required), which is needed for parsing the Apache htpasswd file specified by the -P, --passwords option (see next steps):
2. Create the Apache htpasswd file with at least one user/password pair with this command (you'll be prompted for a password):

htpasswd -sc htpasswd.txt <some_username>
Tip

Read this SO question for running htpasswd cmd under Windows:

http://serverfault.com/questions/152950/how-to-create-and-edit-htaccess-and-htpasswd-locally-on-my-computer-and-then-u

or if you have bogus passwords that you don't care because they are for an internal service (which is still "bad", from a security prespective...) you may use this public service:

http://www.htaccesstools.com/htpasswd-generator/
