---
title:  "Azure DevOps CLI"
categories:
  - posts
tags:
  - azure
  - devops
  - cli
---

Die Azure CLI wird mittlerweile häufig benutzt. Ich verwende eigentlich immer die PowerShell. 
Die gibt es ja mittlerweile auch Cross Platform (pwsh). Unter Windows ist chocolatey ein guter Begleiter (https://chocolatey.org).

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

Als DevOps Organisation verwende ich hier 'tboeker'
https://dev.azure.com/tboeker/


```

# set tboeker as default organization
az devops configure --defaults organization=https://dev.azure.com/tboeker

# list azure devops projects
az devops project list

# create a new azure devops project
az devops project create --name devops-demo --visibility public


```

