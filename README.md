# initRepositoryWithComposer

Command to initialize composer for a repository

  * [Install](#install)
  * [How to](#how-to)
  * [In the box](#in-the-box)
    * [Command line arguments](#in-the-box-command-line-arguments)
    * [Command line options](#in-the-box-command-line-options)
  * [Full composer configuration](#full-composer-configuration)
  * [Contributing](#contributing)

## Install
```bash
composer require --global yoanm/init-repository-with-composer
```

## How to

just type the following
```bash
BIN_PATH/initRepositoryWithComposer path/to/repository/directory "vendor/package-name"
```

In case you launch the command from the repository directory, you can simply use 
```bash
BIN_PATH/initRepositoryWithComposer "vendor/package-name"
```

See below for more information regarding command line options

## In the box

<a name="in-the-box-command-line-arguments"></a>
### Command line arguments

  * `"vendor/package-name"` The package name

<a name="in-the-box-command-line-options"></a>
### Command line options

  * `--type package-type` *Default value is "library"*
  * `--license "LICENSE_TYPE"`
  * `--version "X.Y.Z"`
  * `--description "package description"`
  * `--keywords "KEYWORD1"` *Many allowed*
  * Author *Many allowed*
    * `--author-name "name1"` 
    * `--author-email "email1"` 
    * `--author-role "role1"` 
  * Provided packages *Many allowed*
    * `--provided-package-name "package-1"` 
    * `--provided-package-version "~X.Y"`
  * Suggested packages *Many allowed*
    * `--suggested-package-name "package-1"` 
    * `--suggested-package-description "description1"`
  * Support *Multiple supports allowed*
    * `--support-type "type1"` 
    * `--support-url "url1"`
  * Autoload *Many allowed*
    
    * `--autoload-psr0 "RootNamespace\SubNamespace#path"`
    
      Will append `"\\RootNamespace\\SubNamespace": "path"` under `autoload` -> `psr-0` 
    * `--autoload-psr-4 "RootNamespace\SubNamespace#path"` 
    
      Will append `"\\RootNamespace\\SubNamespace\\": "path"` under `autoload` -> `psr-4` 

  * Autoload dev *Many allowed*
    
    * `--autoload-dev-psr0 "RootNamespace\SubNamespace#path"`
    
      Will append `"\\RootNamespace\\SubNamespace": "path"` under `autoload-dev` -> `psr-0` 
    * `--autoload-dev-psr-4 "RootNamespace\SubNamespace#path"` 
    
      Will append `"\\RootNamespace\\SubNamespace\\": "path"` under `autoload-dev` -> `psr-4` 

  * `--require "vendor/package-name#~x.y"` *Many allowed*
    
      Will append `"vendor/package-name": "~x.y"` under `require`

  * `--require-dev "vendor/package-name#~x.y"` *Many allowed*
    
      Will append `"vendor/package-name": "~x.y"` under `require-dev`
  
  * `--script "script-name#command"` *Many allowed*
  
      Will append `"command"` under `script` -> `script-name` 

```json
"scripts": {
  "script-name": [
    "command"
  ]
}
```

## Full composer configuration

```json
{
  "name": "vendor/package-name",
  "type": "library",
  "license": "LICENSE_TYPE",
  "version": "X.Y.Z",
  "description": "package description",
  "keywords": ["KEYWORD1", "KEYWORD2"],
  "authors": [
    {
      "name": "name1",
      "email": "email1",
      "role": "role1"
    },
    {
      "name": "name2",
      "email": "email2",
      "role": "role2"
    }
  ],
  "provide": {
    "package1": "~x.y",
    "package2": "x.y.z",
  },
  "suggest": {
    "package1": "Description 1",
    "package2": "Description 2",
  },
  "support": {
    "type1": "url1"
  },
  "autoload": {
    "psr-0": {
      "\\RootNamespace\\SubNamespace": "path"
    }
  },
  "autoload-dev": {
    "psr-4": {
      "\\RootNamespace\\SubNamespace\\": "path"
    }
  },
  "require": {
    "requirement1": ">=x.y"
  },
  "require-dev": {
    "requirement1": ">=x.y"
  },
  "scripts": {
    "script-1": [
      "command_1",
      "command_2"
    ],
    "script-2": [
      "command_1",
      "command_2"
    ],
  }
}

```

## Contributing
See [contributing note](./CONTRIBUTING.md)
