# Recyclarr

## What is it?

[Recyclarr](https://github.com/recyclarr/recyclarr){: target=_blank rel="noopener noreferrer" } automatically synchronizes recommended settings from TRaSH guides to your Sonarr/Radarr instances.


| Details     |             |             |             |
|-------------|-------------|-------------|-------------|
| [:material-home: Project home ](https://github.com/recyclarr/recyclarr){: .header-icons target=_blank rel="noopener noreferrer" } | [:octicons-link-16: Docs](https://github.com/recyclarr/recyclarr/wiki){: .header-icons target=_blank rel="noopener noreferrer" } | [:octicons-mark-github-16: Github](https://github.com/recyclarr/recyclarr){: .header-icons target=_blank rel="noopener noreferrer" } | [:material-docker: Docker ](https://ghcr.io/recyclarr/recyclarr){: .header-icons target=_blank rel="noopener noreferrer" }|

### 1. Installation

``` shell

sb install sandbox-recyclarr

```

### 2. Setup

Edit the Recyclarr section in [saltbox `settings.yml`:](../settings.md) and enter your desired update schedule using standard cron syntax.

     ``` { .yaml }
     recyclarr:
       cron_schedule: "@daily"
     ```

Create and edit the file `/opt/recyclarr/recyclarr.yml`. You can run `docker exec recyclarr create-config` to generate a base configuration or create the file separately using the [template](https://github.com/recyclarr/recyclarr/blob/master/src/Recyclarr/config-template.yml). Use the [configuration reference](https://github.com/recyclarr/recyclarr/wiki/Configuration-Reference) and [configuration examples](https://github.com/recyclarr/recyclarr/wiki/Configuration-Examples) to customize.

- Configure Sonarr section
      ``` { .yaml }
      sonarr:
        - base_url: http://sonarr:8989
        - api_key: your_sonarr_api_key
      ```

- Configure Radarr section
      ``` { .yaml }
      radarr:
        - base_url: http://radarr:7878
        - api_key: your_radarr_api_key
      ```

Follow documentation to complete configuration

- [:octicons-link-16: Documentation](https://github.com/recyclarr/recyclarr/wiki/Configuration-Reference){: .header-icons target=_blank rel="noopener noreferrer" }
