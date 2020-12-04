# docker_totara

## Requirements

- Docker
- Docker-compose

## Usage

1. Clone this repository

```
git clone git@github.com:ScottVerbeek/docker_totara.git docker_totara
```

2. Clone Totara code into siteroot

```
cd docker_moodle
git clone git@github.com:XXX/YYY.git siteroot
```

3. Copy site config across

```
cp totara-config siteroot/config.php
```

4. Start containers

```
docker-compose up
```

## Setup Xdebug for VS Code

Open vscode and click `create a launch.json file` then click PHP. VS Code will create a JSON file for you edit it to the following:
```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Listen for XDebug",
            "type": "php",
            "request": "launch",
            "port": 9000,
            "pathMappings": {
                "/siteroot": "${workspaceFolder}"
            }
        },
        {
            "name": "Launch currently open script",
            "type": "php",
            "request": "launch",
            "program": "${file}",
            "cwd": "${fileDirname}",
            "port": 9000
        }
    ]
}
```
