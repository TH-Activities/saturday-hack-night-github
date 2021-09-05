# Saturday Hack Night Template

###What is Saturday Hack Night?
Saturday Hack Night is not just your regular hackathon. Here, we will be building solutions / applications via API integration.
* The needed resource, the respective API and documentation will be shared with you once you register. And remember this is a one time registration! If you have registered once, you need not have to repeat it again for the next.
* API for this week is GitHub API.

###GitHub API
Github APIs( or Github ReST APIs) are the APIs that you can use to interact with GitHub. They allow you to create and manage repositories, branches, issues, pull requests, and many more. For fetching publicly available information (like public repositories, user profiles, etc.), you can call the API. For other actions, you need to provide an authenticated token.
Here are some cool ideas as sample.You can either modify these problem statements in your own way or else you can come up with your own brainstorming super cool ideas.
-Follow my Tree : Ready to create a tree of your followers and then show the followers of your followers and again their followers? Have you though of a final destination or an infinite road that connects like "Followers of  my followers"? Be sharp and ready to shoot it out!!.
- CV Maker : What about creating a CV when you have a awesome profile?

TinkerHub saturday hack night submission repository template. 

### Getting started
This project is only intended to be used by the TinkerHub HQ Staff who organises the hackday.
- Click on [Use this template](https://github.com/tinkerhub/saturday-hack-night-template/generate) button and generate your own version of the project. 
- Update the readme about the project submission process. You can use any data collection tools like airtable to collect the repo URLs from the participants. Use the **Add Project** github action to add a project to the hackday repo.
- Start the hackdday.

### How to use
This repository contains the following GitHub Action workflows:
- Add Project - This will allow organizer to add a new project to the GitHub repository as a submodule so that the project can be evaluated. This contains the following params:
    - Repository URL: URL of the project's repo (HTTPS)
    - Folder Name: You can specify a folder name to keep the submodule (eg: project name)

- You can also trigger the above workflow using the following CURL, replace username and repo with your own username and repo name, also replace the request body with the actual repo and folder name to add:
```bash
export TOKEN="" # get it from https://github.com/settings/tokens
curl --location --request POST 'https://api.github.com/repos/{username}/{repo}/actions/workflows/add-project.yml/dispatches' \
--header 'Authorization: Bearer $TOKEN' \
--header 'Accept: application/vnd.github.v3+json' \
--header 'Content-Type: application/json' \
--data-raw '{
    "ref": "main",
    "inputs": {
        "repo_url": "https://github.com/gautamkrishnar/homebrew-socli.git",
        "folder_name": "homebrew"
    }
}'
```
- Update Projects - This workflow will run every hour updating the submodules to its latest state. It can be also triggered manually from actions tab.

## For Further Queries
If you still have something unclear you can ping us on Discord or ask away in the Saturday Hack Night Channel.

Our core team on discord,
 - @kurian#1209
 - @Rohit T P#8866
 - @Femi#5109 
