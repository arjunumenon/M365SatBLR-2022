# M365 Saturday - Bangalore - 2022

This repository has the artifacts which is used by Arjun Menon in M365 Saturday Bangalore for the session **Turbo-boost your SPFx upgrades and deployment**

## Session Information

Session Link : [M365 Saturday Bangalore](https://www.m365event.com/)

Agenda Link : [Agenda](https://www.m365event.com/#agenda)

![M365 Saturday Bangalore](./assets/M365Bangalore-Dec2022-ArjunMenon.jpg)

## Session Abstract

In this session, Arjun talks about [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) and through the tool how you can turbo-boost your [SPFx](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/sharepoint-framework-overview) upgrades and deployment.

## Demo Details

### Pre-requisites

1. Node.JS
2. [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/user-guide/installing-cli/#install-the-cli-for-microsoft-365)
3. Node Version Manager (NVM)
   1. For switching between Node.JS versions
4. CodeTour VS Code Extension. Here is the [link](https://marketplace.visualstudio.com/items?itemName=vsls-contrib.codetour) for the same

### Demo Codes

For the complete demo, we have used one of the PnP WebParts, which is available in the [link](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-groups-teams).

Following are the demo which as showcased in the session.

#### 1) Demo 1 - SPFx Doctor

Command : [`m365 spfx doctor`](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/)

##### 1.1) Steps

1. Go to the Demo Folder : [Source Original](codes-demo/source-original/)
2. Run `npm install` to install the dependencies
3. Switch to an older Node Version (10.6.0)
4. Run the command  `m365 spfx doctor --output text`
5. It will show the result and the suggestions.

#### 2) Demo 2 - SPFx Project Upgrade

Here we will be upgrading the SPFx project from Version 1.12.0 to 1.13.0

Command : [`m365 spfx project upgrade`](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/)

##### 2.1) Steps

1. Go to the Demo Folder : [Source Original](codes-demo/source-original/)
2. Run `npm install` to install the dependencies
3. Run the command  `m365 spfx project upgrade --toVersion 1.13.0 --shell powershell --output md > "upgrade-report.md"`
   1. You can also run `m365 spfx project upgrade --toVersion 1.13.0 --shell powershell --output tour`
   2. The above will give the result in CodeTour format
   3. You can get more details on getting the result from [this link](https://marketplace.visualstudio.com/items?itemName=vsls-contrib.codetour#opening-tours)
4. It will show the result in the report format
5. Execute the actions either one by one or via summary
6. The sample of the upgraded project could be found from [Source Upgraded](codes-demo/source-upgraded/)
7. Run `gulp build`

#### 3) Demo 3 - SPFx Project Doctor

Command : [`m365 spfx project upgrade`](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-doctor/)

##### 3.1) Steps

1. Go to the Demo Folder : [Source Upgraded](codes-demo/source-original/)
2. Run `gulp bundle`
3. You can see some errors on the code
4. Run the command `m365 spfx project doctor --output text`
5. Complete the actions mentioned in the report
6. Run `gulp bundle`
7. You can see that the errors which was there after the upgrade is fixed now

#### 4) Demo 4 - SPFx in CI/CD Pipeline

The demo was planned to be shown based on the blog from here. You can follow the same steps which is explained on the blog.
Here is the blog which you can follow : [SPFx in CI/CD Pipeline](https://arjunumenon.com/ci-cd-spfx-deployment-azure-devops-m365-cli/)
