PHP7
=========

Install PHP7 from source

Requirements
------------

Development Tools and respective header file for compiling PHP7 must be present on system

Role Variables
--------------

	php7_buildrequires

List of required packages to be installed for compiling PHP7 from source

	php7_source_url

Url with PHP7 source archive

	php7_source_checksum

Expected checksum of downloaded archive

	php7_user_name
	php7_user_group
	php7_user_homedir
	php7_user_shell
	php7_user_gecos

System user information. This user is created and used for compiling PHP7

	php7_build

PHP7 build

	php7_sefcontext:
	  - setype:
	    target:

List of SeLinux patterns for fixing new files

	php7_root_dir: "/opt/php7"
	php7_fpm_exec: "{{php7_root_dir}}/sbin/php-fpm"
	php7_etc_dir: "{{php7_root_dir}}/etc"
	php7_bin_dir: "{{php7_root_dir}}/bin"
	php7_fpm_config_file: "{{php7_etc_dir}}/php-fpm.conf"
	php7_pool_config_dir: "{{php7_etc_dir}}/php-fpm.d"
	php7_lib_dir: "{{php7_root_dir}}/lib"
	php7_var_dir: "{{php7_root_dir}}/var"
	php7_log_dir: "{{php7_var_dir}}/log"

Filesystem structure of compiled PHP7

	php7_global_pidfile: "{{php7_var_dir}}/run/php7-fpm.pid"
	php7_global_errorlog: "{{php7_log_dir}}/error.log"
	php7_global_loglevel: "notice"
	php7_global_maxproc: 0
	php7_global_emergency_restart_threshold: 10
	php7_global_emergency_restart_interval: "1m"
	php7_global_process_control_timeout: 0
	php7_global_process_priority: 0

Global php-fpm settings

	php7_pools: []
	#  - pool_name: "www"
	#    prefix: "/srv/websites/test"
	#    user: "nobody"
	#    listen: "php7.sock"

List of configuration settings for php-fpm pools.

	php7_install_prefix: "--prefix {{php7_root_dir}}"
	php7_configure: "{{php7_install_prefix}} --disable-all --enable-fpm --with-fpm-systemd"

Those are variables for configuring PHP7 compilation
Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
