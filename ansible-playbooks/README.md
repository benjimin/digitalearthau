# Module Deployment on the NCI

Proposal for available DEA modules at the NCI.

There will be a set of modules available for Python 3:

  digitalearthau/stable (default, link to latest)
  digitalearthau/develop (latest successful build)
  
  digitalearthau/1.4.1
  digitalearthau/1....

These will rely upon and automatically load 

  digitalearthau-env/stable
  digitalearthau-env/YYYYMMDD (many)
  
  digitalearthau-env/develop (regularly updated)



Environment
  Unstable
    digitalearthau/develop
    digitalearthau-env/......
    
  Stable
    


To update the `develop` env
    
    ansible-playbook python-env.yml -e 

All of the environment modules should be able to share the same head conda installation,
which can have all the different environments contained within.
 
 


## Questions

* Do we want to stick with Conda install + Conda Env
  - Is it possible to install environment contents into the default env?
  
* Or should we have one central conda install, with conda managed environments within...

* Versioning? ODC and DEA should have different version numbers.
  

This directory contains a starting point for more maintainable system for deploying datacube code
modules onto the NCI.

At the moment it can install the agdc-statistics module, but can hopefully be extended to setting up
all the other modules.

After loading `agdc-py3` and installing ansible to `$HOME` it can be run with:

    ansible-playbook -v -v -i "localhost," -c local install-stats-module.yml
    


