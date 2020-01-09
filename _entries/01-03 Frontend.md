---
sectionid: frontend
sectionclass: h2
title: Create Weather App frontend
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
<summary>Create Blazor Server App</summary>

Run the following commands:

```sh
..\[repo name]> mkdir src\client
..\[repo name]> cd .\src\client\
..\[repo name]\src\client> dotnet new blazorserver
```

![Blazor Server create](media/dotnet/blazorservercreate.png)

Run the new web app and open the page in your browser on http://localhost:5000/

```sh
..\[repo name]\src\client> dotnet run
```

![Running App from localhost](media/dotnet/blazorapplocalhost.png)
</details>
<details>
<summary>Commit and push files to GitHub</summary>

Stage and commit your files. Push them to your GitHub repo. As an extra challenge you can look at the help for git (--help) and see if you can combine some of the actions. Or perhaps only push part of the files. Be sure to also check `git status` to see that everything looks right.

```sh
..\[repo name]\src\client> git add .
..\[repo name]\src\client> git commit -m 'Blazor App'
..\[repo name]\src\client> git push
```
</details>
