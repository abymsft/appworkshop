---
sectionid: webapi
sectionclass: h2
title: Create Weather Web API backend
parent-id: intro
---

### Challenges
* Create a folder in your local git repo for the frontend - e.g. src/client
* Standing in that directory scaffold a new 'blazorserver' project using `dotnet new`
* Verify that the project runs on localhost
* Commit the files and push to your GitHub repo


#### Challenge verification

#### Tips

#### Step-by-step solution

<details>
<summary>Create Web API</summary>

Run the following commands:

```sh
..\[repo name]\src\client> cd ..
..\[repo name]\src> mkdir server
..\[repo name]\src> cd .\server\
..\[repo name]\src\server> dotnet new webapi
..\[repo name]\src\server> dotnet run
```

</details>

<details>
<summary>Test the Web API</summary>
Access the new web api from your browser on http://localhost:5000/weatherforecast

You can also test this from command line - depending on your shell, either wget, curl or Invoke-WebRequest. For example:

```sh
..\[repo name]\src\server> curl https://localhost:5001/weatherforecast
```

```powershell
..\[repo name]\src\server> Invoke-WebRequest http://localhost:5000/weatherforecast
```

You should see an output similar to this (probably more compressed depending on your tool):

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

<details>
<summary>Certificate errors?</summary>
If you get a certificate error, you can either trust the dev cert, if you have permissions to do so.

```sh
..\[repo name]\src\server> dotnet dev-certs https --trust
```

Or you can run the commands in "ignore" mode:

```sh
..\[repo name]\src\server> curl --ignore https://localhost:5001/weatherforecast
```

```powershell
..\[repo name]\src\server> Invoke-WebRequest -SkipCertificateCheck http://localhost:5000/weatherforecast
```

</details>

<details>
<summary>Commit and push files to GitHub</summary>

Stage and commit your files. Push them to your GitHub repo.

```sh
..\[repo name]\src\server> git add .
..\[repo name]\src\server> git commit -m 'Weather Web API'
..\[repo name]\src\server> git push
```
</details>
