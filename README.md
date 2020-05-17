
# DEPRECATED REPO

This repo is trasfered [here](https://github.com/U-Company/infrastructure)

# Private docker registry
This is manual for starting docker image for private docker registry. You can see docker-hub [page](https://hub.docker.com/_/registry).

# Start

    docker-compose up

# Password

If you want to set password for your registry, you need set into docker-compose path to volumes:

    - $HOME/.credentionals:/auth
    
You need to use htpassword. 

1. First make sure you have the passlib module installed (note that passlib>=1.6 is required), which is needed for parsing the Apache htpasswd file specified by the -P, --passwords option (see next steps):
2. Create the Apache htpasswd file with at least one user/password pair with this command (you'll be prompted for a password):


        htpasswd -sc htpasswd.txt <some_username>

    You can use [this](http://www.htaccesstools.com/htpasswd-generator/) generator.
3. Add password to $HOME/.credentionals/htpasswd to a new line and restart docker-registry server
    
# Communicate with registry

Before push, you need [login](https://docs.docker.com/engine/reference/commandline/login/):

    docker login <url>
    
Set tag for image:

    docker tag <image-id> <url>/<tag>

After that, docker asks you login and password. Now, you can push concrete image by tag:

    docker push <url>/<tag>
    
Now, you can see your image into registry by endpoint (with authentication):

    <url>/v2/_catalog
   
Downloading image from registry by tag:

    docker pull <url>/<tag>
    
More info about docker registry API, you can find [here](https://docs.docker.com/registry/spec/api/).
    
# References

You can see more info:

* [SSL](https://habr.com/ru/post/320884/)
* [docker-registry API](https://docs.docker.com/registry/spec/api/)
    


