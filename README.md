# Create webhooks with GitHub API

This code example takes in a file with a list of GitHub repositories and uses a `config.py` file containing the required credentials, org, and so on, to either list or create webhooks in each repo.

To use these scripts, clone this repository locally. These scripts have been tested with Python 3.8.

## Credentials

You'll need to create a personal access token using the instructions at https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token. Treat this token as you would a password and only give it the minimum permissions needed for the automation tasks.
* To run against an org, you must have the `admin:org` scope for the token.

## Config file
```
gh_username = "username"
gh_api_key = "9d1f1dcf---c58b5032a" # Create from Settings > Profile > Developer settings > Personal access token, scope should be admin:repo_hook
gh_orgname = "organizationname"
gh_secret = "d954a2----dde787" # This value is inserted in the payload for creating a webhook that requires a secret
```

## File containing list of repositories

Create a text file with one repo name per line, and be sure not to add an extra new line at the end of the file. If you have an extra new line, the script will return with "Not Found" for the last "repo name" in the file.

## Usage

Once you have your config file and a list of repositories in a text file, you can run the script like so:

```
python create_webhook.py repolist.txt
```
