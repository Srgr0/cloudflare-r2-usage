# Cloudflare R2 Usage (GitHub Actions)
Automatically fetch and save the bucket size of Cloudflare R2.  

## How-to Use
1. Get your Account ID and bucket name on the Cloudflare dashboard. See [this article](https://developers.cloudflare.com/fundamentals/get-started/basic-tasks/find-account-and-zone-ids/) which may be helpful in finding your Account ID.  
2. Open the [API token page](https://dash.cloudflare.com/profile/api-tokens) and create a new token. Select 'Create Custom Token' and grant read permissions for Workers R2 Storage.  
3. Create a new repository and navigate to repo/Settings/Secrets/Actions to set up the following secrets:  
 - Name: account_id, Secret: YOUR_CLOUDFLARE_ACCOUNT_ID
 - Name: bucket_name, Secret: YOUR_CLOUDFLARE_R2_BUCKET_NAME
 - Name: api_token, Secret: YOUR_CLOUDFLARE_API_TOKEN
Please don't forget to replace the secret values with the ones you obtained earlier.  
4. Move to repo/Settings/Actions/General and select 'Read and write permissions' under Workflow permissions. Write access is necessary to save the execution results within the repository.  
5. Go to repo/Actions and select Configure for Simple Workflow. Paste the contents of actions.yml in this repository into the editing field.  
6. GitHub Actions will be executed every hour, and the results will be saved in the output.csv file. Additionally, you can manually run it at any time from repo/Actions.

## Note
GitHub Actions can be run in both public and private repositories, each with its own advantages and disadvantages.  
- Public Repository
   - The usage of Actions is free.
   - The logs and execution results of Actions are public and can be seen by anyone.
- Private Repository
   - The logs and execution results of Actions can only be seen by users with access to the repository.
   - Actions are billed on a pay-as-you-go basis. A certain usage amount is allocated each month according to your plan, and charges occur if you exceed it.

This information is current as of July 16, 2023.  
