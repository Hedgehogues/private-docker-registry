# docker-registry
This is docker-image for private docker-registry

If you want to set password for your registry, you need set into docker-compose path to volumes:

    - $HOME/.credentionals:/auth
    
You need to use htpassword. You can see details about htpassword into [pypiserver repo](https://github.com/Hedgehogues/pypiserver). This is the same case.
