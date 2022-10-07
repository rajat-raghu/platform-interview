## structural changes
### Previously
```
├── tf
│   ├── README.MD
│   ├── dev.tf
│   ├── main.tf
│   ├── prod.tf
│   └── staging.tf
```
### Now
```
├── tf
│   ├── README.MD
│   ├── dev.tf
│   ├── main.tf
│   ├── prod.tf
│   └── staging.tf
```

### Highlights
* Tf file on the bases of environment for better code seggrigation on environment bases.
* Code commenting in staging tf file for better code structure undertanding 
 
 ## Adding New Environment

 1 Updated docker-compose.yaml
 * Added network named "staging" for seprate network configuration
 * Added Service for key vault named "staging" to deploy keyvault in staging env.
 * Added host port "8401" & updated value of VAULT_DEV_ROOT_TOKEN_ID for staging env.

2 Updated stanging.tf file
*  Created following resources & configration for key vault: vault_audit, vault_auth_backend, vault_generic_secret, vault_policy, vault_generic_endpoint
*  Created & configured following application container: account_staging, gateway_staging, payment_staging, frontend_staging
* Updated secrets, evironment variables, netwroking settings, keyvault policies for the staging environment