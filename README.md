# Azure_NodeJS_RunNpmLint
This template is used for linting that analyses source code for potential errors, style violations, and other issues. This Template used for code analysis of nodeJS.

## Parameters:

The pipeline requires the following parameters to be defined:

| Name | type | Default | Required/Optional | Comments |
| :-------------: | :-------------: | ------------- | :-------------: | :-------------: |
| filePath | String | $(Build.SourcesDirectory) | Required | define the filepath or working directory for package.json. Youc can also pass arguements  if required |
| npmLint | string | lint  | Optional | The value depends on command specified in package.json.Youc can also pass arguements  if required |


These parameters provide multiple use case options for the template, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

You can directly call a particular template as per the requirement. for example: 

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: your_username/Azure_NodeJS_RunNpmLint
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'

  steps:
  # passing the parameters
  - template: Azure_NodeJS_RunNpmLint.yml
    parameters:
        filePath: ${{ parameters.filePath }}
        npmLint: ${{ parameters.npmLint }}
        
Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.

  ```
