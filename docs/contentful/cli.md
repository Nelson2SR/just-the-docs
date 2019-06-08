---
layout: default
title: CLI
published: true
nav_order: 1
parent: Contentful
---

## Contentful CLI

> Contentful provides a content infrastructure for digital teams to power content in websites, apps, and devices. Unlike a CMS, Contentful was built to integrate with the modern software stack. It offers a central hub for structured content, powerful management and delivery APIs, and a customizable web app that enable developers and content creators to ship digital products faster.

## Usage

### Install

```sh
npm install -g contentful-cli
```

### Account

* login (open new browser and get token)

```sh
contentful login
```

* logout

```sh
contentful logout
```

### Space

* list space

```sh
contentful space list
```

* create space

```sh
contentful space create --name {space-name}
```

* delete space

```sh
contentful space delete --space-id {space-id} --yes
```

### Environment

* list space environment

```sh
contentful space environment list --space-id {space-id}
```

* delete space environment

```sh
contentful space environment delete --space-id {space-id} --environment-id{environment-id} --management-token {management-token}
```

* create space environment (using data of master environment)

```sh
contentful space environment create --space-id {space-id} --environment-id{environment-id} --name {name}
```

### Export/Import

* export data of environment

```sh
contentful space export --config {export-config.json}
```

For exporting data, either attribute or config file is supported. "--include-archived" hasn't been supported yet.  "--download-assets" make it abled to download assets in your content file location. Without "--download-assets", the exported json still contain data of assets and able to import into new environment.

The export-config.json could be the following format:

```json
{
  "spaceId": "gqdhiiwuk2b4",
  "environmentId": "master",
  "managementToken": "CFPAT-ApATgnOWx8TCI7h2O_n0gN-_f_TZfpQNHMaa62kRguM",
  "exportDir": "/Users/surong/Desktop/ssg/",
  "saveFile": true,
  "contentFile": "contentful-exported-data.json",
  "skipContentModel": false,
  "skipContent": false,
  "skipRoles": false,
  "skipWebhooks": false,
  "contentOnly": false,
  "includeDrafts": true,
  "maxAllowedLimit": 1000,
  "errorLogFile": "/Users/surong/Desktop/ssg/exportErrorlog"
}
```

* import data with json

```sh
contentful space import --config {import-config.json}
```

For importing data, either attribute or config file is supported. webhook can only imported into master environment.

The import-config.json could be the following format:

```json
{
  "spaceId": "gqdhiiwuk2b4",
  "managementToken": "CFPAT-ApATgnOWx8TCI7h2O_n0gN-_f_TZfpQNHMaa62kRguM",
  "environmentId": "uat-test",
  "contentFile": "/Users/surong/Desktop/ssg/contentful-gqdhiiwuk2b4-master.json",
  "contentModelOnly": false,
  "skipContentModel": false,
  "skipLocales": false,
  "skipContentPublishing": false,
  "noUpdate": false,
  "errorLogFile": "/Users/surong/Desktop/ssg/importErrorlog"
}
```
