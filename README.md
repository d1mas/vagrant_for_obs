Vagrantfile and script for testing "obs-server" puppet module.
===============
In this repo you'll find initial script and Vagrantfile itsalve.

1. Create a dir ``mkdir obs-server-tsts`` and go into it ``cd obs-server-tests``
2. Clone this repo inside ``git clone https://github.com/d1mas85/vagrant_for_obs.git . ``
3. Clone puppet manifests repo ``git clone ssh://_username_@_gerrit_url_:_gerrit_port_/_path_to_/_manifests_``
3. Run the initial script ``./vagrant_env_setup `` which shall download needwd VagrantBox with few checks
4. Use Vagrant commands further
