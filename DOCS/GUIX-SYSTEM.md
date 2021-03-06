# system

A system is an operating system config with services.

## info
´´´
guix system 
   search           search for existing service types
 --list-image-types list available image types
´´´


## system profile admin

´´´
guix system 
   describe         reproduce system data

   extension-graph  emit the service extension graph in Dot format
   shepherd-graph   emit the graph of shepherd services in Dot format

   init             initialize a root file system to run GNU
   reconfigure      switch to a new operating system configuration
   roll-back        switch to the previous operating system configuration
   list-generations list the system generations
   switch-generation switch to an existing operating system configuration
   delete-generations delete old system generations

    guix system container --list-image-types list available image types

´´´


# export 
´´´
guix system 
 build            build the operating system without installing anything
   container        build a container that shares the host's store
   vm               build a virtual machine image that shares the host's store
   vm-image         build a freestanding virtual machine image
   image            build a Guix System image
   docker-image     build a Docker image

    --share=SPEC       for 'vm' and 'container', share host file system with
                         read/write access according to SPEC
      --expose=SPEC      for 'vm' and 'container', expose host file system
                         directory as read-only according to SPEC
  -N, --network          for 'container', allow containers to access the network
  -r, --root=FILE        for 'vm', 'vm-image', 'image', 'container',
                         and 'build', make FILE a symlink to the result, and
                         register it as a garbage collector root
  -v, --verbosity=LEVEL  use the given verbosity LEVEL


´´´

Export systems

guix system vm config.scm
guix system docker-image config.scm
guix system container config.scm


guix copy --from=remote-host    one off copy
guix pack -f docker dovecot       Exporting for Use Outside of Guix
                                                   pack pass software to non Guix users.
       guix pack --format=docker python python-numpy
guix publish                                Serve Packages


# Sample configurations
Several configs     https://github.com/Millak/guix-config/blob/master/vm_config.scm
Big setup:             https://github.com/alezost/guix-config
Services               https://lists.gnu.org/archive/html/help-guix/2019-05/msg00262.html




# Containers
Guix can also generate docker images

https://github.com/pjotrp/guix-notes/blob/master/CONTAINERS.org
Orchestration: 
https://gitlab.com/pjotrp/guix-notes/-/blob/master/DEPLOY.org



Webbrowser Like emacs
https://nyxt.atlas.engineer/faq

guix copy --to=Benutzer@Rechner \
          coreutils `readlink -f ~/.guix-profile`

guix system container my-config.scm \
   --expose=$HOME --share=$HOME/tmp=/exchange


