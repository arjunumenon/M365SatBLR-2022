# Upgrade project source-upgraded to v1.13.0

Date: 12/5/2022

## Findings

Following is the list of steps required to upgrade your project to SharePoint Framework version 1.13.0. [Summary](#Summary) of the modifications is included at the end of the report.

### FN001001 @microsoft/sp-core-library | Required

Upgrade SharePoint Framework dependency package @microsoft/sp-core-library

Execute the following command:

```sh
npm i -SE @microsoft/sp-core-library@1.13.0
```

File: [./package.json:15:5](./package.json)

### FN001002 @microsoft/sp-lodash-subset | Required

Upgrade SharePoint Framework dependency package @microsoft/sp-lodash-subset

Execute the following command:

```sh
npm i -SE @microsoft/sp-lodash-subset@1.13.0
```

File: [./package.json:16:5](./package.json)

### FN001003 @microsoft/sp-office-ui-fabric-core | Required

Upgrade SharePoint Framework dependency package @microsoft/sp-office-ui-fabric-core

Execute the following command:

```sh
npm i -SE @microsoft/sp-office-ui-fabric-core@1.13.0
```

File: [./package.json:17:5](./package.json)

### FN001004 @microsoft/sp-webpart-base | Required

Upgrade SharePoint Framework dependency package @microsoft/sp-webpart-base

Execute the following command:

```sh
npm i -SE @microsoft/sp-webpart-base@1.13.0
```

File: [./package.json:18:5](./package.json)

### FN001008 react | Required

Upgrade SharePoint Framework dependency package react

Execute the following command:

```sh
npm i -SE react@16.13.1
```

File: [./package.json:24:5](./package.json)

### FN001009 react-dom | Required

Upgrade SharePoint Framework dependency package react-dom

Execute the following command:

```sh
npm i -SE react-dom@16.13.1
```

File: [./package.json:25:5](./package.json)

### FN001021 @microsoft/sp-property-pane | Required

Install SharePoint Framework dependency package @microsoft/sp-property-pane

Execute the following command:

```sh
npm i -SE @microsoft/sp-property-pane@1.13.0
```

File: [./package.json:14:3](./package.json)

### FN001022 office-ui-fabric-react | Required

Upgrade SharePoint Framework dependency package office-ui-fabric-react

Execute the following command:

```sh
npm i -SE office-ui-fabric-react@7.174.1
```

File: [./package.json:23:5](./package.json)

### FN002001 @microsoft/sp-build-web | Required

Upgrade SharePoint Framework dev dependency package @microsoft/sp-build-web

Execute the following command:

```sh
npm i -DE @microsoft/sp-build-web@1.13.0
```

File: [./package.json:32:5](./package.json)

### FN002002 @microsoft/sp-module-interfaces | Required

Upgrade SharePoint Framework dev dependency package @microsoft/sp-module-interfaces

Execute the following command:

```sh
npm i -DE @microsoft/sp-module-interfaces@1.13.0
```

File: [./package.json:33:5](./package.json)

### FN002003 @microsoft/sp-webpart-workbench | Required

Remove SharePoint Framework dev dependency package @microsoft/sp-webpart-workbench

Execute the following command:

```sh
npm un -D @microsoft/sp-webpart-workbench
```

File: [./package.json:35:5](./package.json)

### FN002009 @microsoft/sp-tslint-rules | Required

Upgrade SharePoint Framework dev dependency package @microsoft/sp-tslint-rules

Execute the following command:

```sh
npm i -DE @microsoft/sp-tslint-rules@1.13.0
```

File: [./package.json:34:5](./package.json)

### FN002015 @types/react | Required

Install SharePoint Framework dev dependency package @types/react

Execute the following command:

```sh
npm i -DE @types/react@16.9.51
```

File: [./package.json:30:3](./package.json)

### FN002018 @microsoft/rush-stack-compiler-3.9 | Required

Install SharePoint Framework dev dependency package @microsoft/rush-stack-compiler-3.9

Execute the following command:

```sh
npm i -DE @microsoft/rush-stack-compiler-3.9@0.4.47
```

File: [./package.json:30:3](./package.json)

### FN006004 package-solution.json developer | Optional

In package-solution.json add developer section

```json
{
  "solution": {
    "developer": {
      "name": "",
      "privacyUrl": "",
      "termsOfUseUrl": "",
      "websiteUrl": "",
      "mpnId": "Undefined-1.13.0"
    }
  }
}
```

File: [./config/package-solution.json:3:5](./config/package-solution.json)

### FN007002 serve.json initialPage | Required

Update serve.json initialPage URL

```json
{
  "initialPage": "https://enter-your-SharePoint-site/_layouts/workbench.aspx"
}
```

File: [./config/serve.json:5:3](./config/serve.json)

### FN007003 serve.json api | Required

From serve.json remove the api property

```json

```

File: [./config/serve.json:6:3](./config/serve.json)

### FN010001 .yo-rc.json version | Recommended

Update version in .yo-rc.json

```json
{
  "@microsoft/generator-sharepoint": {
    "version": "1.13.0"
  }
}
```

File: [./.yo-rc.json:5:5](./.yo-rc.json)

### FN012017 tsconfig.json extends property | Required

Update tsconfig.json extends property

```json
{
  "extends": "./node_modules/@microsoft/rush-stack-compiler-3.9/includes/tsconfig-web.json"
}
```

File: [./tsconfig.json:2:3](./tsconfig.json)

### FN015007 config\copy-assets.json | Required

Remove file config\copy-assets.json

Execute the following command:

```sh
Remove-Item "config\copy-assets.json"
```

File: [config\copy-assets.json](config\copy-assets.json)

### FN024001 Create .npmignore | Required

Create the .npmignore file


File: [./.npmignore](./.npmignore)

### FN005002 deploy-azure-storage.json workingDir | Required

Update deploy-azure-storage.json workingDir

```json
{
  "workingDir": "./release/assets/"
}
```

File: [./config/deploy-azure-storage.json:3:3](./config/deploy-azure-storage.json)

### FN017001 Run npm dedupe | Optional

If, after upgrading npm packages, when building the project you have errors similar to: "error TS2345: Argument of type 'SPHttpClientConfiguration' is not assignable to parameter of type 'SPHttpClientConfiguration'", try running 'npm dedupe' to cleanup npm packages.

Execute the following command:

```sh
npm dedupe
```

File: [./package.json](./package.json)

## Summary

### Execute script

```sh
npm un -D @microsoft/sp-webpart-workbench
npm i -SE @microsoft/sp-core-library@1.13.0 @microsoft/sp-lodash-subset@1.13.0 @microsoft/sp-office-ui-fabric-core@1.13.0 @microsoft/sp-webpart-base@1.13.0 react@16.13.1 react-dom@16.13.1 @microsoft/sp-property-pane@1.13.0 office-ui-fabric-react@7.174.1
npm i -DE @microsoft/sp-build-web@1.13.0 @microsoft/sp-module-interfaces@1.13.0 @microsoft/sp-tslint-rules@1.13.0 @types/react@16.9.51 @microsoft/rush-stack-compiler-3.9@0.4.47
npm dedupe
Remove-Item "config\copy-assets.json"
```

### Modify files

#### [./config/package-solution.json](./config/package-solution.json)

In package-solution.json add developer section:

```json
{
  "solution": {
    "developer": {
      "name": "",
      "privacyUrl": "",
      "termsOfUseUrl": "",
      "websiteUrl": "",
      "mpnId": "Undefined-1.13.0"
    }
  }
}
```

#### [./config/serve.json](./config/serve.json)

Update serve.json initialPage URL:

```json
{
  "initialPage": "https://enter-your-SharePoint-site/_layouts/workbench.aspx"
}
```

From serve.json remove the api property:

```json

```

#### [./.yo-rc.json](./.yo-rc.json)

Update version in .yo-rc.json:

```json
{
  "@microsoft/generator-sharepoint": {
    "version": "1.13.0"
  }
}
```

#### [./tsconfig.json](./tsconfig.json)

Update tsconfig.json extends property:

```json
{
  "extends": "./node_modules/@microsoft/rush-stack-compiler-3.9/includes/tsconfig-web.json"
}
```

#### [./.npmignore](./.npmignore)

Create the .npmignore file:

```text
!dist
config

gulpfile.js

release
src
temp

tsconfig.json
tslint.json

*.log

.yo-rc.json
.vscode

```

#### [./config/deploy-azure-storage.json](./config/deploy-azure-storage.json)

Update deploy-azure-storage.json workingDir:

```json
{
  "workingDir": "./release/assets/"
}
```
