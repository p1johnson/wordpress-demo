# Wordpress Demo

## Deployment instructions

- Fork to new GitHub repository
- Create resource group and service principal
```
az group create -l <location> -n <resource group name>
az ad sp create-for-rbac --role contributor --scope <resource group id> --name <seret name>
```

- Copy output from serice principal creation to repository secret `AZURE_CREDENTIALS`
- Create secret `AZURE_SUBSCRIPTION` and provide subscription id
- Create secret `AZURE_RESOURCE_GROUP` and provide resource group name
- Create secret `MYSQL_ADMINISTRATOR_PASSWORD` and provide a random secure password
- Edit the `/templates/parameters.json` file to provide resource names

Check-in the files and run the `Deploy Template` GitHub action