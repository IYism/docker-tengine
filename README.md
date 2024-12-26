# Tengine Docker Image

This repository provides multi-operating system Docker images for Tengine, designed for high-performance web applications. It supports Lua scripting, PCRE2, GMSSL, and more (via Tongsuo).

## Features

- **GMSSL Support**: Provides cryptographic functions compliant with national standards.
- **Lua Scripting**: Use LuaJIT with the lua-nginx-module for dynamic request handling and flexible configuration.
- **PCRE2 Support**: Enhanced regular expressions with JIT compilation for improved performance.
- **Brotli Compression**: Efficient compression for faster loading of static resources.

## Quick Start

### Build the Docker Image

Build the Docker image locally:
```sh
docker build -t sungyism/tengine:latest .
```

### Run the Container

You can run the Tengine container using the following command:
```sh
docker run -d -p 80:80 -p 443:443 --name tengine sungyism/tengine:latest
```

This will start Tengine with the default configuration.

### Custom NGINX Configuration

You can customize the NGINX configuration by mounting your own configuration files into the container:
```sh
docker run -d \
  -v /etc/nginx:/etc/nginx \
  -v /data/public:/data/public \
  -p 80:80/tcp \
  -p 443:443/tcp \
  --name tengine \
  sungyism/tengine:latest
```

You can also include custom Lua scripts, or other configuration options as needed.

### Tengine Compilation Parameters
The following parameters were used to compile Tengine:
```sh
--with-threads
--with-file-aio
--with-http_ssl_module
--with-http_v2_module
--with-http_realip_module
--with-http_addition_module
--with-http_xslt_module
--with-http_image_filter_module
--with-http_geoip_module
--with-http_sub_module
--with-http_dav_module
--with-http_flv_module
--with-http_mp4_module
--with-http_gunzip_module
--with-http_gzip_static_module
--with-http_auth_request_module
--with-http_random_index_module
--with-http_secure_link_module
--with-http_degradation_module
--with-http_slice_module
--with-http_stub_status_module
--without-http_upstream_keepalive_module
--with-mail
--with-mail_ssl_module
--with-stream
--with-stream_ssl_module
--with-stream_realip_module
--with-stream_geoip_module
--with-stream_ssl_preread_module
--with-stream_sni
--with-compat
--with-pcre
--with-pcre-jit
--add-module=modules/ngx_tongsuo_ntls
--add-module=modules/mod_common
--add-module=modules/mod_config
--add-module=modules/mod_dubbo
--add-module=modules/mod_strategy
--add-module=modules/ngx_backtrace_module
--add-module=modules/ngx_http_concat_module
--add-module=modules/ngx_http_footer_filter_module
--add-module=modules/ngx_http_proxy_connect_module
--add-module=modules/ngx_http_reqstat_module
--add-module=modules/ngx_http_slice_module
--add-module=modules/ngx_http_sysguard_module
--add-module=modules/ngx_http_trim_filter_module
--add-module=modules/ngx_http_upstream_check_module
--add-module=modules/ngx_http_upstream_consistent_hash_module
--add-module=modules/ngx_http_upstream_dynamic_module
--add-module=modules/ngx_http_upstream_dyups_module
--add-module=modules/ngx_http_upstream_iwrr_module
--add-module=modules/ngx_http_upstream_keepalive_module
--add-module=modules/ngx_http_upstream_session_sticky_module
--add-module=modules/ngx_http_upstream_vnswrr_module
--add-module=modules/ngx_http_user_agent_module
--add-module=modules/ngx_multi_upstream_module
--add-module=modules/ngx_slab_stat
```


## Contributing

Contributions are welcome! Please feel free to submit issues, pull requests, or suggestions.
