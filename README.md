# Minecraft NGINX Reverse Proxy
This repo contains an NGINX  reverse proxy config for a Minecraft server running a java server with geyser enabled (bedrock) at the same time.  This is useful if you want to run a small proxy server in the cloud to hide the real IP address of your Minecraft server to add a layer of abstraction for DDOS attempts (the cloud server is likely to go down first and certain cloud providers may be able to detect some forms of DDOS and absorb the traffic).

It could also be useful if you ever needed to perform proxy_passing with both TCP and UDP (non-HTTP traffic) through an NGINX proxy.

To use this in your own setup, replace the following values with your own:

```
<replace_with_nginx_server_ip> - The IP address of the NGINX server this configuration is installed on
<replace_with_minecraft_server_ip> - The IP address of the Minecraft server that you are proxying to
```

> ⚠️ You must have the `ngx_stream_core_module` and `ngx_http_proxy_module` modules installed for the `stream` and `proxy pass` directives to function! (see [this](https://nginx.org/en/docs/stream/ngx_stream_core_module.html) and [this](https://nginx.org/en/docs/http/ngx_http_proxy_module.html) respectively)
