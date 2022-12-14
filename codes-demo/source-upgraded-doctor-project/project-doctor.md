# Validate project source-upgraded-doctor-project

Date: 12/5/2022

## Findings

Following is the list of issues found in your project. [Summary](#Summary) of the recommended fixes is included at the end of the report.

### FN021005 @types/es6-promise installed as a dependency | Required

Package @types/es6-promise is installed as a dependency. Install it as a devDependency instead

Execute the following command:

```sh
npm i -DE @types/es6-promise@0.0.33
```

File: [./package.json:20:5](./package.json)

### FN021005 @types/react-dom installed as a dependency | Required

Package @types/react-dom is installed as a dependency. Install it as a devDependency instead

Execute the following command:

```sh
npm i -DE @types/react-dom@16.8.3
```

File: [./package.json:21:5](./package.json)

### FN021005 @types/webpack-env installed as a dependency | Required

Package @types/webpack-env is installed as a dependency. Install it as a devDependency instead

Execute the following command:

```sh
npm i -DE @types/webpack-env@1.13.1
```

File: [./package.json:22:5](./package.json)

### FN021007 Obsolete @microsoft/rush-stack-compiler-2.9 found in devDependencies | Required

Multiple rush-stack-compiler packages found. Uninstall obsolete @microsoft/rush-stack-compiler-2.9

Execute the following command:

```sh
npm un -D @microsoft/rush-stack-compiler-2.9
```

File: [./package.json:30:22](./package.json)

### FN002013 @types/webpack-env | Required

Install missing package @types/webpack-env

Execute the following command:

```sh
npm i -DE @types/webpack-env@1.13.1
```

File: [./package.json](./package.json)

### FN002016 @types/react-dom | Required

Install missing package @types/react-dom

Execute the following command:

```sh
npm i -DE @types/react-dom@16
```

File: [./package.json](./package.json)

### FN002019 @microsoft/rush-stack-compiler-3.9 | Required

Uninstall unsupported version of @microsoft/rush-stack-compiler

Execute the following command:

```sh
npm un -D @microsoft/rush-stack-compiler-2.9
```

File: [./package.json:30:22](./package.json)

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
npm un -D @microsoft/rush-stack-compiler-2.9 @microsoft/rush-stack-compiler-2.9
npm i -DE @types/es6-promise@0.0.33 @types/react-dom@16.8.3 @types/webpack-env@1.13.1 @types/webpack-env@1.13.1 @types/react-dom@16
npm dedupe
```
