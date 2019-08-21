---
title:  "Azure DevOps CLI 2"
categories:
  - posts
tags:
  - azure-cli
  - azure-devops-cli
  - azure-pipelines
---

Nachdem wir ein neues Projekte angelegt haben legen wir jetzt ein neues Repository an.
Anschließend clonen wir das repo und legen eine neue Pipeline an

```

# list repositories
az repos list --project devops-demo

# create a new repository
az repos create --project devops-demo --name demo.devops

# get remote url and clone
$cloneUrl = (az repos show --project devops-demo --repo demo.devops --query 'remoteUrl' --output tsv)

git clone $cloneUrl

```

Dann ein neue Pipeline Datei einfügen.

```
# azure-pipelines.yml
# https://aka.ms/yaml

trigger:
  branches:
    include: 
    - master

pool:
  vmimage: 'ubuntu-16.04'

steps:

- pwsh: Write-Host 'Hallo Welt'
  displayName: 'hello world'

```

Die Datei commiten und pushen

```

git add .
git commit -m "added pipeline definition"
git push

```

Jetzt eine neue Pipeline anlegen

```
# create pipeline
az pipelines create --name demo.devops.p1 --branch master --project devops-demo --repository demo.devops --repository-type tfsgit --skip-first-run --yml-path azure-pipelines.yml

# run pipeline
az pipelines run --name demo.devops.p1 --branch master --project devops-demo

```

mehr folgt dann demnächst...
