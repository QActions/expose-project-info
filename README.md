# expose-project-info
Exposes the project name and version as environment variables.
Requires the runner to support bash (docker images will not run this action).

Reads `documentation/project_info.json` and adds `PROJECT_NAME` and `PROJECT_VERSION` to the environment variables (`GITHUB_ENV`).

Example usage:
```yml
jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Expose project info
        uses: QActions/expose-project-info@1.0.0
      
      # Hereafter the PROJECT_NAME and PROJECT_VERSION environment variables are available.
```
