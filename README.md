<div align="center">
  <h1 align="center">cap-create-app</h1>
    <br />
</div>
<br />

## Acknowledgments
 This project is based on https://github.com/Turutupa/cf-create-app

## About The Project

This project is meant to simplify the initial configuration needed to create and deploy an end-to-end application to a Cloud Foundry account in SAP Cloud Platform.

What cap-create-app does for you?

1. Creates a basic CAP application
2. Adds a simple React, Angular or Vue application to your project
3. Adds an HTML5 Deployer to the project
4. Adds an Application Router to the project
5. Adds the HTML5 Application Repository service (app-host and app-runtime) to the project
6. Adds the Authentication and Authorization service (XSUAA) to the project
7. Bind all modules together as a MTA application, ready to be deployed in a Cloud Foundry environment


<!-- GETTING STARTED -->

## Getting Started

Setting and end-to-end application in SAP Cloud Platform is not a trivial task.

This tool creates a project with all the components you need to build (and easily deploy) a web application with a CAP backend exposing OData services, and an HTML5 application ready to consume those services.

### Prerequisites

| Pre-requisite | Description
| ------------- | ----------------------------------------------------------------------
| Node.js v12   | Required runtime for this boilerplate. Recommended install it with NVM
| cf cli        | Cloud Foundy CLI tool
| cds cli       | npm i @sap/cds-dk
### Cloud prerequisites

To be able to deploy this application you need an SAP Cloud Platform account in the Cloud Foundry (CF) environment.

In your CF account space, the following services must be available:

- HTML5 Application Repository | `html5-apps-repo`
- SAP HANA Schemas & HDI Containers | `hana`
- Authorization & Trust Management | `xsuaa`


## Usage

### Create your app

Open a terminal in your workspace directory and run:

```sh
npx cap-create-app YOUR_APP_NAME
```
In the comand prompt, choose the frontend framework you prefer

The new project contains these folders and files, following the recommended project layout:

| File / Folder    | Purpose                                                                                                   |
| ---------------- | --------------------------------------------------------------------------------------------------------- |
| `app/`           | content for UI frontends go here                                                                          |
| `approuter/`     | Application Router configuration files                                                                    |
| `db/`            | your domain models and data go here                                                                       |
| `html5Deployer/` | helper application to deploy HTML5 apps to the HTML5 Application Repository service in SAP Cloud Platform |
| `srv/`           | your service models and code go here                                                                      |
| `package.json`   | project metadata and configuration                                                                        |
| `README.md`      | this getting started guide                                                                                |

### Add your business logic

- Add/modify entities to your DB schema on `db/` folder
- Add/modify services to your backend app in the `srv/` folder
- Add/modify your custom HTML5 application in the `app/` folder
- Modify the Application Router behaviour on `approuter/xs-app.json`

### Deploy the app

Open a terminal in the project root directory and run:

```sh
mbt build
cf deploy mta_archives/yourAppMtarArchiveName.mtar
```

## License

Distributed under the MIT License.

Project Link: [https://github.com/franciscofreitas2001/cf-create-app](https://github.com/franciscofreitas2001/cf-create-app)
