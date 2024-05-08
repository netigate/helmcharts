# Netigate daas cronjob

This chart support the creation of a kubernetes cronjob.  
It can consume kafka/postgres credentials from Hashicorp Vault.  
Application secrets from Vault must reside in your daas `mount path` within Vault.

Example:

You daas project is named `data-integration` and you have a job named `my-daily-job`.
Within Vault, your must create a secret named `my-daily-job` in mount path `data-integration`.  
Only then can you consume the secret in your cronjob.
