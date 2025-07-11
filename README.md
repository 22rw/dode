[do.de](https://www.do.de) module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with [do.de](https://www.do.de).

## Caddy module name

```
dns.providers.dode
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "dode",
				"api_token": "YOUR_PROVIDER_API_TOKEN"
			}
		}
	}
}
```

or with the Caddyfile:

### globally
```
{
	acme_dns dode <api_token>
}
```

### one site
```
example.com {
	respond "Hello World"
	tls {
		dns dode <api_token>
	}
}
```
