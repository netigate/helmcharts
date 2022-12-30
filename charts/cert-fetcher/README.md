## cert-fetcher readme

Pull certificates from Vault to your kubernetes namespace

## How-to
You must specify the address of Vault for targeted environment. It will then spin up
a injector pod that pulls secrets to a local volume. And then the vault kubernetes agent
will read from the volume to create tls secret objects.

You may view available certificates in repo `self-service` in path `src/kubernetes/namespace`.  
Or, you can to go target environments vault, login with OIDC, and look in path `certificates/` to get names.

the name of the certificates represents the friendly name, not commot name of the certificate.  
ex: `wildcard-example-com` represents common name `*.example.com`

## Schema
```yaml
vaultAddress: "" # https://fqdn-to-vault
namespace: "" #target_namespace
name: "" # same name as your deployment name
certificates:
  - vaultSecretName: "" # one or many key/values for available certificates
```
