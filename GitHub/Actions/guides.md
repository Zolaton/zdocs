# GitHub Action Guides

## [Publishing Docker images](https://docs.github.com/en/actions/guides/publishing-docker-images)
* [Publish to DockerHub](https://github.com/Zolaton/zdocs/blob/edf982ff48630f91e103dc22fba8e43456752cb1/.github/workflows/dockerhub-publish.yml#L1)
* [Publish as GitHub package](https://github.com/Zolaton/zdocs/blob/edf982ff48630f91e103dc22fba8e43456752cb1/.github/workflows/docker-github-publish.yml#L1)
* [Publish to DockerHub & as GitHub package](https://github.com/Zolaton/zdocs/blob/edf982ff48630f91e103dc22fba8e43456752cb1/.github/workflows/docker-multi-reg-publish.yml#L1)

## [Deploying to Amazon Elastic Container Service](https://docs.github.com/en/actions/guides/deploying-to-amazon-elastic-container-service)
* TODO

## [Deploying to Azure App Service](https://docs.github.com/en/actions/guides/deploying-to-azure-app-service)
### [Prerequisites](https://docs.github.com/en/actions/guides/deploying-to-azure-app-service#prerequisites)
* Run:
  ```bash
  az login
  # Create resource group
  az group create -l canadaeast -n mikatu
  # Create an Azure App Service plan
  az appservice plan create --resource-group mikatu --name jikalo-service-plan --is-linux
  # Create a web app.
  az webapp create --name jikalo-web --plan jikalo-service-plan --resource-group mikatu --runtime "node|10.14"
  ```
* Configure an Azure publish profile and create an `AZURE_WEBAPP_PUBLISH_PROFILE` secret. (See [Generate deployment credentials](https://docs.microsoft.com/en-us/azure/app-service/deploy-github-actions?tabs=applevel#generate-deployment-credentials) and [Encrypted secrets](https://docs.github.com/en/actions/reference/encrypted-secrets#creating-encrypted-secrets-for-a-repository))
### Deploying to Azure Workflow
* See [workflow code](https://github.com/Zolaton/zdocs/blob/11324953d167ed173abc05b9ef74b84a3567f72c/.github/workflows/azure-publish.yml#L1).

## [Deploying to Google Kubernetes Engine](https://docs.github.com/en/actions/guides/deploying-to-google-kubernetes-engine)
### [Prerequisites](https://docs.github.com/en/actions/guides/deploying-to-google-kubernetes-engine#prerequisites)
* Run
  ```bash
  # Create project
  gcloud container clusters create lozatar-cluster --project=mulqatu-project --zone=us-east4-b

  ```
* TODO: to be completed. Depends on billing?

## [Using GitHub Actions for project management](https://docs.github.com/en/actions/guides/using-github-actions-for-project-management)
### Examples
* [Adding labels to issues](https://github.com/Zolaton/zdocs/blob/23205062e169ba19cff4540ca2524e23db591b5d/.github/workflows/add-label-to-issues.yml#L1)
* [Removing a label when a card is added to a project board column](https://github.com/Zolaton/zdocs/blob/27e2c3fb3a518b170dcbfe220a64080ec8bc8782/.github/workflows/remaining-open-issues.yml#L1)
* [Moving assigned issues on project boards](https://github.com/Zolaton/zdocs/blob/6aca6212bc05fb65579e6532ee05301d6e72cb64/.github/workflows/moving-assigned-issues.yml#L1)
* [Commenting on an issue when a label is added](https://github.com/Zolaton/zdocs/blob/774489f3162697e2e9edf1b19a4ae4d7195fe280/.github/workflows/comment-on-label.yml#L1)
* [Closing inactive issues](https://github.com/Zolaton/zdocs/tree/feac24e638024f5850a6d24ffa409d59d2aeac01)
* [Scheduling issue creation](https://github.com/Zolaton/zdocs/blob/7e3f5c04f16741d309475b5eddfe8747b3b01d0f/.github/workflows/create-issue.yml#L1)

## [Using GitHub CLI in workflows](https://docs.github.com/en/actions/guides/using-github-cli-in-workflows)
Code examples:
* [Comment action opening](https://github.com/Zolaton/zdocs/blob/f7ef081197348e04be3140b4b1e87b40ae6ef706/.github/workflows/greet-issuer.yml#L1)
* [Execute API calls through GitHub CLI](https://github.com/Zolaton/zdocs/blob/39c07c2197d672836791bf7a53e1720efcee357e/.github/workflows/remaining-open-issues.yml#L1)
