---
sectionid: prereq
sectionclass: h2
title: Prerequisites
parent-id: intro
---

### Tools

As the core tools, you will need Azure CLI, dotnet CLI and a Git client. Further, we will use Visual Studio Code to edit files. These are all compatible with both Windows, Linux and Mac.

You can use the Azure Cloud Shell accessible at <https://shell.azure.com> once you login with an Azure subscription. The Azure Cloud Shell has the Azure CLI pre-installed and configured to connect to your Azure subscription as well as `dotnet` and `git`.

### Azure subscription
You will need an Azure subscription to complete the challenges. It should work on all subscription types and with Contributor permissions for just a Resource Group. If you experience otherwise, please let us know in the issues section in the GitHub repo for the workshop, so we can improve.

#### If you have an Azure subscription

<details>
<summary>Expand details</summary>

Please use your username and password to login to <https://portal.azure.com>.

Also please authenticate your Azure CLI by running the command below on your machine and following the instructions. Ensure you are in the right subscription.

```sh
az login
az account show
```

</details>

#### If you have been given an access to a subscription as part of a lab, or you already have a Service Principal you want to use

<details>
<summary>Expand details</summary>

If you have lab environment credentials similar to the below or you already have a Service Principal you will use with this workshop,

![Lab environment credentials](media/lab-env.png)

Please then perform an `az login` on your machine using the command below, passing in the `Application Id`, the `Application Secret Key` and the `Tenant Id`.

```sh
az login --service-principal --username APP_ID --password "APP_SECRET" --tenant TENANT_ID
```

</details>

#### Azure Cloud Shell

You can use the Azure Cloud Shell accessible at <https://shell.azure.com> once you login with an Azure subscription.

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
