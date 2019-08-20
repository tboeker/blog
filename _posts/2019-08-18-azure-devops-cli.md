---
title:  "Azure DevOps CLI"
categories:
  - posts
tags:
  - azure-cli
  - azure-devops-cli
---

Die Azure CLI wird mittlerweile häufig benutzt. Ich verwende eigentlich immer die PowerShell. 
Die gibt es ja mittlerweile auch Cross-Platform [pwsh](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell). Unter Windows ist [chocolatey](https://chocolatey.org) ein guter Begleiter.

Es wird Zeit, die Azure DevOps CLI auszuprobieren. 
Vorher aber erstmal installieren. PowerShell als Administrator öffnen: 

```

# install azure-cli
choco install azure-cli

# upgrade azure-cli
choco upgrade azure-cli

# install devops extension
az extension add --name azure-devops

```

Einloggen bei Azure

```

# login to az cli
az login

```

Als DevOps Organisation verwende ich hier [tboeker](
https://dev.azure.com/tboeker/)

Also konfigurieren und ein devops-demo Projekt anlegen

```

# set tboeker as default organization
az devops configure --defaults organization=https://dev.azure.com/tboeker

# list azure devops projects
az devops project list

# create a new azure devops project
az devops project create --name devops-demo --visibility public

```

mehr folgt dann demnächst...