---
sectionid: appservicebuild
sectionclass: h2
title: Deploy to App Service using native build
parent-id: intro
---

This is a challenge section


#### Create App Service Web App

Now we want to host our Web API in Azure. We will use an App Service Web App for this. Web Apps run on App Service Plans. Plans can be of type Windows or Linux and come in various sizes and feature sets. For this workshop, the Linux Standard SKU will be used, but feel free to play with other options. Throughout the scripts, some standard values are used for names and regions, but you can modify that if you like.

```sh
..\[repo name]> az group create --name appworkshop-group --location westeurope
..\[repo name]> az appservice plan create --name appworkshop-plan --resource-group appworkshop-group --sku S1 --is-linux
```

For the Web App we need a global unique name - put on your creative hat.

```sh
..\[repo name]> az webapp create -g appworkshop-group --name mycreativeuniquename --plan appworkshop-plan --runtime "DOTNETCORE|3.0" --deployment-source-url https://github.com/madsd/apptest --deployment-source-branch master
..\[repo name]> az appservice plan create --name appworkshop-plan --resource-group appworkshop-group --sku S1 --is-linux
```

