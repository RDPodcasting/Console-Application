####Estrutura
                
+ Mytemplate
+ .template.config
    + template.json
+ MyProject.Console.csproj
+ Program.cs

####Template.json
```javascript
{
    "author": "Thiago de Melo Lima",
    "classifications": [ "Console" ], 
    "name": "RD Console Template",
    "generatorVersions": "[1.0.0.0-*)",
    "description": "An empty project template for creating an .NET Core application.",
    "identity": "Template.MyProject.Console",         
    "groupIdentity":"Template.MyProject",
    "shortName": "rdconsole",
    "tags": {
      "language": "C#",
      "type":"project"
    },
    "sourceName": "MyProject.Console",
    "preferNameDirectory": true, 
    "guids": [
      "53bc9b9d-9d6a-45d4-8429-2a2761773502"
    ],
    "sources": [
      {
        "modifiers": [
          {
            "condition": "(ExcludeLaunchSettings)",
            "exclude": [
              "bin/",
              "obj/"
            ]
          }
        ]
      }
    ],
    "symbols": {  
      "ExcludeLaunchSettings": {
      "type": "parameter",
      "datatype": "bool",
      "defaultValue": "false",
      "description": "Whether to exclude launchSettings.json from the generated template."
    },
      "copyrightYear": {
        "type": "generated",
        "generator": "now",
        "replaces": "copyrightYear",
        "parameters": {
          "format": "yyyy"
        },
        "skipRestore": {
          "type": "parameter",
          "datatype": "bool",
          "description": "If specified, skips the automatic restore of the project on create.",
          "defaultValue": "false"
        },
        "title": {
          "type": "parameter",
          "defaultValue": "Hello Word",
          "replaces":"MyProject Console"
        },
        "primaryOutputs": [
          {
            "path": "MyProject.Console.csproj"
          }
        ],
        "defaultName": "MyProject Console",
        "postActions": [
          {
            "condition": "(!skipRestore)",
            "description": "Restore NuGet packages required by this project.",
            "manualInstructions": [
              {
                "text": "Run 'dotnet restore'"
              }
            ],
            "actionId": "210D431B-A78B-4D2F-B762-4ED3E3EA9025",
            "continueOnError": true
          }
        ]
      }
    }
}
```