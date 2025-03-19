# Log Monitoring System

The system is designed to collect and analyze application logs.
- To download the project, enter the git clone command.
```sh
git clone https://github.com/tarkoman4ik/log-monitoring-system.git
```
- After clonning start [Docker desktop][docker-url]. If it isn't installed, then you'll have to install, otherwise the project will not start.
- After that navigate to directory where project has been installed and configure filebeat & logstash configs.
```sh
filebeat.inputs:
  - type: log
    paths:
      - /var/logs/#your expression for log files
    fields:
      app_name: "application name"
    json.keys_under_root: true     
    json.add_error_key: true

  - type: log
    paths:
      - /var/logs/#your expression for log files
    fields:
      app_name: "application name"
    json.keys_under_root: true    
    json.add_error_key: true
```
- Change paths to your application in .env file
- After all the settings are configured, run the compose command
 ```sh
 docker-compose up -d --build
```
[docker-url]: <https://docs.docker.com/desktop/setup/install/windows-install/>
