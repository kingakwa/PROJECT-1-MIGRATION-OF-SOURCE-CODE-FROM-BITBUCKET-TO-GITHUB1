# PROJECT 1: MIGRATION OF SOURCE CODE FROM BITBUCKET TO GITHUB

# Mirror-and-synchronizing (BITBUCKET TO GITHUB MIGRTION AND SYNCRONIZATION)

Mirror and synchronizing GitHub & Bitbucket repository.

# OBJECTIVE: Migrating your existing bitbucket repository to GitHub repository, synchronizing them in shuch a way that when ever a change is made in the source repository(Bitbucket) the same change will be replecated in GitHub without any manuel intervention.
https://github.com/kingakwa/Mirror-and-synchronizing-akwa/blob/main/migration-bitbucket-github.jpg

# Prerequisites
Before starting, ensure you have:

- A Bitbucket repository with admin access
- A GitHub account with repository creation permissions
- SSH and Git installed on your local machine
- Basic knowledge of CI/CD pipelines

 # Project Visualization:
<img width="531" alt="Image" src="https://github.com/user-attachments/assets/fe2a1db7-157b-41b5-89a2-0f0365ebce85" />

# Step-by-Step Guide

## On GitHub, create a new empty repository
- Go to GitHub
- Click on New Repository
- Do not initialize with a README file
- Copy the repository UR

 ## On your Bitbucket
 
- Navigate to your Bitbucket repository Example "Mirroring-Repo" Create an access token under `Repository settings > Security > Access tokens`
 - Create Repository Access Token with selecting all the "READ" Permission
  - Copy the last Access token Example [{ "https://x-token-auth:ATCTT3xFfGN0TSG5xC5PMZex1aEWC2wMY7j1SiYTwLpR7WTpHQ4DJ1oRfevWbd-LVn9bRzmr3csDN4DEjT57KYlsxWcKXnk5zW17DLJ9ssRcOFFwegxzPTMS-MAfumre3yDmXup-z1nHb8XSRGI9N_McR6FRyHArzIoPIWiJSk6cQfYqfAkIw_w=65FC4ty63@bitbucket.org/demo-migration12/solstice_demo.git" }](https://bitbucket.org/solavisetech-migration/aws-etl-tf-python-project/src/master/)
<img width="902" alt="Image" src="https://github.com/user-attachments/assets/aece45e6-4c91-485a-9a56-4e6fd7ad2687" />
   
- Navigate To Github and Import the Repository while keeping the same name "Mirroring-Repo"
     - To navigate to GitHub and import a repository while keeping the same name "Mirroring-Repo", follow these steps:
       
       Step 1: Log in to GitHub
     - Open GitHub in your browser.
     - Sign in with your GitHub credentials.

       Import a Repository
     - Click on your profile icon in the top-right corner.
     - Select "Your repositories" from the dropdown.
      - Click the green "New" button and select "Import a repository" (or go directly to GitHub Importer).
     - Enter the URL of the repository you want to import (e.g., from GitHub, GitLab, or Bitbucket).
     - In the "Repository Name" field, type "Mirroring-Repo" to maintain the same name.
     - Choose your preferred visibility (Public or Private).
     - Click "Begin Import" and wait for the process to complete.
      <img width="640" alt="Image" src="https://github.com/user-attachments/assets/2b141862-190f-4b89-8e7e-57c4d114c841" />

 
  - On Bitbucket, Enable Pipelines under Repository settings > Pipelines > Settings
      <img width="920" alt="Image" src="https://github.com/user-attachments/assets/fa17fba2-1fac-489e-8c3a-a61b7dd48387" />
      
  - On Bitbucket, Generate keys under Repository settings > Pipelines > SSH keys. Copy the public key to clipboard
    <img width="918" alt="Image" src="https://github.com/user-attachments/assets/76f97f39-dd11-4b00-8056-ac5983003a67" />

  - On the same page, under Known hosts enter github.com as the Host address and then click Fetch followed by Add host
   <img width="914" alt="Image" src="https://github.com/user-attachments/assets/64680c3e-4db6-48d1-b0bd-378692c1450e" />

  - On GitHub, add the public key under Settings > Security > Deploy keys > Add deploy key. Tick the checkbox to Allow write access
  <img width="758" alt="Image" src="https://github.com/user-attachments/assets/38a6bb39-deea-47ed-9c54-0260488e453f" />
    
  - On Bitbucket, add the public key under Repository settings > Security > Access keys > Add key
  - <img width="767" alt="Image" src="https://github.com/user-attachments/assets/7fb246c1-ba06-43c3-bf4d-e6f921a2710e" />
  
  - On Bitbucket, Create an access tokens under Repository settings > Security > Access tokens. Create Repository Access Token, give a name with selecting all the "READ" Permission and tick the checkbox of Webhooks
  - Copy the first Token Example { "ATCTT3xFfGN0TSG5xC5PMZex1aEWC2wMY7j1SiYTwLpR7WTpHQ4DJ1oRfevWbd-LVn9bRzmr3csDN4DEjT57KYlsxWcKXnk5zW17DLJ9ssRcOFFwegxzPTMS-MAfumre3yDmXup-z1nHb8XSRGI9N_McR6FRyHArzIoPIWiJSk6cQfYqfAkIw_w=65FC4ty63" }
    
<img width="890" alt="Image" src="https://github.com/user-attachments/assets/ee02de26-507f-4890-8ba6-9d9de95a3458" />
  - On Bitbucket, Create a Repository variables under Repository Settings > Pipeline > Repository variable. Naming the variable Example " BITBUCKET_VARIABLE"
    
<img width="931" alt="Image" src="https://github.com/user-attachments/assets/0f947334-09bb-4329-9a59-462157cc2c3b" />    
  - On Github, At the top right click on your Profile, Scroll down at the bottom click on settings
    
<img width="919" alt="Image" src="https://github.com/user-attachments/assets/f4bdbba7-fecb-46b2-8b10-2867b899eb94" />  
  - At the bottom left of the page click Developer Settings, Create a Personal access tokens Under Personal access tokens > Token (classic) > Generate new token > Generate new token (classic)> copy the token and past on the github `repository variable` for `value`  
    
<img width="931" alt="Image" src="https://github.com/user-attachments/assets/32e92700-a030-4107-a36f-16621db568ea" />    
  - Check the "repo" box, "Workflow" box and the "write:package" box. Genarate Token and copy the token Example "ghp_zY5GxaeytuAZlR4tPcwqovPz7c2ZVy1kdfg"
   
<img width="929" alt="Image" src="https://github.com/user-attachments/assets/f0ced948-f117-4d7d-a773-0c618288ffe4" />
  
  - On Bitbucket, Create a Repository variables with the Access Token from Github under Repository Settings > Pipeline > Repository variable. Naming the variable Example "GITHUB_VARIABLE"

# Inside the Bitbucket repo, create a bitbucket-pipelines.yml file containing the following:

```
  pipelines:
    default:
      - step:
          name: Sync GitHub Mirror
          image: alpine/git:latest
          clone:
            enabled: false
          script:
            - git clone --mirror https://x-token-auth:"$BITBUCKET_VARIABLE"@bitbucket.org/demo-migration12/Mirroring-Repo.git ## @bitbucket.org follow by your Bitbucket repository path
            - cd Mirroring-Repo.git ## cd followed by your Github repository Name
            - git push --mirror https://x-token-auth:"$GITHUB_VARIABLE"@github.com/asaphdanchi/Mirroring-Repo.git ## @github.com followed by your Github repository path
```

On your code replace the "$BITBUCKET_VARIABLE" and "$GITHUB_VARIABLE" with your corresponding variable names while keeping the $ and the "" sign. 

# Run the pipeline in Bitbucket
-On the Bitbucket, select pipeline and select `Run piple` line at the right corner and watich the pipeline run to success with a green indication that it was successful

<img width="953" alt="Image" src="https://github.com/user-attachments/assets/e5525c8d-acdd-45e4-bf6f-1a07c682b3b5" />
-Pipe line successful after two attempt 
<img width="944" alt="Image" src="https://github.com/user-attachments/assets/f525a19c-b4f0-4b04-8de3-6c845283b949" />
-Any change on the main repo automatically triger and synronise with the gitHub repo.

## Test the Pipeline

- Test file was created in bitbucket repo and it automatically syncronised with the gitHub repo https://github.com/kingakwa/Testing-migratio
- Commit and push the bitbucket-pipelines.yml file to Bitbucket.
- Navigate to Bitbucket Repository > Pipelines
- Manually trigger the pipeline or push a change to test.
- Verify that the repository is correctly mirrored to GitHub.
