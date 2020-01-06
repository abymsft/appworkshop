---
sectionid: webapi
sectionclass: h1
title: Creating a Web API
parent-id: intro
---

### Tasks

#### Create .Net Core Web API

First we need an end point to fetch data. The dotnet cli conveniently has template which create a Web API for a Weather forecast service. Let's try that.
* First open a shell of preference. Cmd, PowerShell (Core), Bash, ...
* Then check that you have at least version [.Net Core 3.1.100](https://dotnet.microsoft.com/download) installed: `dotnet --version`.
* Next create a folder to host the project. Since we will be adding this to git, an good folder structure is of good use. An example (..\github\[account name]\[repo name]\src\weatherforecast)

```sh
..\[repo name]> git init
..\[repo name]> dotnet new gitignore
```

```sh
..\[repo name]> mkdir src\weatherforecast
..\[repo name]> cd .\src\weatherforecast\
..\[repo name]\src\weatherforecast> dotnet new webapi
```

#### Test Web API

Test out the new Web API with the run command. You Web API should now be listening on localhost port 5000/5001.

```sh
..\[repo name]\src\weatherforecast> dotnet run
```

Choose your method of preference for testing out the API. This could be curl, Postman or simply the browser. The Web API will not be listening for incoming messages in the root folder, so you need to access it on https://localhost:5001/weatherforecast. You should see an output similar to this:

<details>
<summary>Web API output</summary>

```json
[
    {
        "date": "2019-12-24T07:05:54.4477534+01:00",
        "temperatureC": 42,
        "temperatureF": 107,
        "summary": "Scorching"
    },
    {
        "date": "2019-12-25T07:05:54.4477888+01:00",
        "temperatureC": 54,
        "temperatureF": 129,
        "summary": "Freezing"
    },
    {
        "date": "2019-12-26T07:05:54.4477895+01:00",
        "temperatureC": 45,
        "temperatureF": 112,
        "summary": "Cool"
    },
    {
        "date": "2019-12-27T07:05:54.4477898+01:00",
        "temperatureC": -20,
        "temperatureF": -3,
        "summary": "Hot"
    },
    {
        "date": "2019-12-28T07:05:54.4477901+01:00",
        "temperatureC": 26,
        "temperatureF": 78,
        "summary": "Bracing"
    }
]
```

</details>

#### Add Web API to source control

Start by creating a new repo in GitHub: https://github.com/new (do not initialize with any files).

![New Git Repo](media/github/newrepo.png)

Navigate to the root of the repo folder and add a reference to your GitHub repo and then stage (add) the files.

```sh
..\[repo name]> git remote add origin https://github.com/[account name]/[repo name]
..\[repo name]> git add .
..\[repo name]> git status
```

Check that all files are staged and then commit:

![Git Status](media/github/gitstatus.png)

The commit and push the files (-u to initially set upstream repo and branch).

```sh
..\[repo name]> git commit -m 'Initial commit'
..\[repo name]> git push -u origin master
```

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

