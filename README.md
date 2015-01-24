Features
--------

- nginx init script to run nginx as as service
- idempotent execution
- helloWorld example server configuration deployment
- abort if OS not Debian

Instructions
-------------------


Edit inventory file
	
	vim test

Update host information there. Currently set to localhost


Update playbook :

	vim test.yml

Update host group name for which to run roles against. Currently configured to run for all hosts listed under the group "loadBalancer"

Finally, fire up the command

	$ ansible-playbook -i test test.yml   --ask-pass -u ubuntu --ask-sudo-pass -v

If you're already root, then

	$ ansible-playbook -i test test.yml  --ask-pass -v



Enable/Disable modules
------------------------


You can disable module given below as per requirement.

	--without-ngx_devel_kit_module --without-lua_cjson  --without-lua_redis_parser  --without-lua_rds_parser  --without-lua_resty_dns --without-lua_resty_memcached  --without-lua_resty_redis  --without-lua_resty_mysql  --without-lua_resty_upload  --without-lua_resty_upstream_healthAuthRequestNginxModule  --without-lua_resty_string  --without-http_coolkit_module  --without-lua_resty_websocket   --without-lua_resty_lock  --without-lua_resty_lrucache   --without-lua_resty_core  --without-select_module   --without-poll_module --without-http_charset_module  --without-http_gzip_module  --without-http_ssi_module   --without-http_userid_module  --without-http_access_module  --without-http_auth_basic_module  --without-http_autoindex_module  --without-http_geo_module --without-http_map_module   --without-http_split_clients_module  --without-http_referer_module  --without-http_rewrite_module  --without-http_proxy_module  --without-http_fastcgi_module  --without-http_uwsgi_module   --without-http_scgi_module   --without-http_memcached_module  --without-http_limit_zone_module --without-http_limit_req_module  --without-http_empty_gif_module  --without-http_browser_module  --without-http_upstream_ip_hash_module --without-http  --without-http-cache  --without-mail_pop3_module   --without-mail_imap_module  --without-mail_smtp_module  --without-pcre


study `configure` in openResty tar file to get enabled and disabled modules list

Edit **roles/openResty/tasks/main.yml** file and find task name "configuring openResty". By Editing this task you can enable or disable module list.