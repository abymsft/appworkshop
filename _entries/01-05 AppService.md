---
sectionid: appservicebuild
sectionclass: h2
title: Deploy to App Service using native build
parent-id: intro
---

### Challenges
* Create App Service Plan (Linux or Windows)
* Create Web App for frontend
* Set source control project reference in Web App App Settings
* Enable native (kudu) build from GitHub source
* Repeat for backend


#### Challenge verification

#### Tips

#### Step-by-step solution

<details>
<summary>Create App Service Plan</summary>

Now we want to host our web resources in Azure. We will use an App Service Web Apps for this. Web Apps run on App Service Plans. Plans can be of type Windows or Linux and come in various sizes and feature sets. For this workshop, the Linux Standard SKU will be used, but feel free to play with other options. Throughout the scripts, some standard values are used for names and regions, but you can modify that if you like.
Your Resource Group should already be created in the Git Init section. Now run the following command:

```sh
az appservice plan create --resource-group <Resource-Group-Name> --name appworkshop-plan --sku S1 --is-linux

```

</details>

<details>
<summary>Create App Service Web App</summary>

To create the Web App, you can run the following command. Remember to replace the needed values.

```sh
az webapp create -g <Resource-Group-Name> --name <Unique-WebApp-Name> --plan appworkshop-plan --runtime '"DOTNETCORE|Latest"'
```

As we have multiple project in the source repo, we need to tell the build engine which project to build. We do this by specifying the PROJECT setting:
```sh
az webapp config appsettings set -g <Resource-Group-Name> --name <Unique-WebApp-Name> --settings PROJECT='src/client\client.csproj'
```

Now we can setup the build:

```sh
az webapp deployment source config -g <Resource-Group-Name> --name <Unique-WebApp-Name> --repo-url https://github.com/[account]/[repo] --branch master
```

Wait about a minute, and your web app should be available at https://<Unique-WebApp-Name>.azurewebsites.net

Repeat the steps for the backend Web API.
