---
sectionid: prereq
sectionclass: h2
title: Prerequisites
parent-id: intro
---

### Tools

As the core tools, you will need Azure CLI, dotnet CLI and a Git client. Further, we will use Visual Studio Code to edit files. These are all compatible with both Windows, Linux and Mac.

For central source control and ci/cd, the workshop will be using GitHub, so you also need to have a GitHub account. If you prefer another set of tools and repos - like Azure DevOps Repos and Pipelines, the workshop can be completed with that, but you will not have step-by-step solutions, and in the challenges you should just replace GitHub with your tool-of-choice.

All the challenges will also be using .Net Core, but except for the code specific challenges, you can replace it with a web application in your language-of-choice.

You can use the Azure Cloud Shell accessible at <https://shell.azure.com> once you login with an Azure subscription. The Azure Cloud Shell has the Azure CLI pre-installed and configured to connect to your Azure subscription as well as `dotnet` and `git`.

### Azure subscription

You will need an Azure subscription to complete the challenges. It should work on all subscription types and with Contributor permissions for just a Resource Group. If you experience otherwise, please let us know in the issues section in the GitHub repo for the workshop, so we can improve.

#### Working locally

<details>
<summary>Expand details</summary>

Pick your favorite Shell. On Windows it can be WSL, Git Bash, PowerShell (Core) or good'ol cmd.

Ensure the tools are installed. Azure CLI (at least 2.0.76) and .Net Core SDK (at least 3.1.100). Verify the versions with `az --version` and `dotnet --list-sdks`. Git should also be of recent update 2.20+.

* Install Azure CLI: <https://docs.microsoft.com/en-us/cli/azure/install-azure-cli>
* Install .Net Core SDK: <https://dotnet.microsoft.com/download>
* Install Git client: <https://git-scm.com/download>

If you want to use Visual Studio Code, you can find it here <https://code.visualstudio.com/download> - but any text editor will work

Also please authenticate your Azure CLI by running the command below on your machine and following the instructions. Ensure you are in the right subscription.

```sh
az login
az account show
```
</details>

#### Azure Cloud Shell

You can use the Azure Cloud Shell accessible at <https://shell.azure.com> once you login with an Azure subscription. If you need to configure Azure Cloud Shell first, you find the details below.

<details>
<summary>Expand details</summary>

Head over to <https://shell.azure.com> and sign in with your Azure Subscription details.

Select **Bash** as your shell.

![Select Bash](media/cloudshell/0-bash.png)

Select **Show advanced settings**

![Select show advanced settings](media/cloudshell/1-mountstorage-advanced.png)

Set the **Storage account** and **File share** names to your resource group name (all lowercase, without any special characters), then hit **Create storage**

![Azure Cloud Shell](media/cloudshell/2-storageaccount-fileshare.png)

You should now have access to the Azure Cloud Shell

![Set the storage account and fileshare names](media/cloudshell/3-cloudshell.png)

</details>

#### Uploading and editing files in Azure Cloud Shell

<details>
<summary>Expand details</summary>

- You can use `code <file you want to edit>` in Azure Cloud Shell to open the built-in text editor.
- You can upload files to the Azure Cloud Shell by dragging and dropping them
- You can also do a `curl -o filename.ext https://file-url/filename.ext` to download a file from the internet.

</details>
