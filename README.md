# changelog-gen

__ALPHA - IN ACTIVE DEVELOPMENT__

A command line interface application to generate changelogs.

The changelog consist of the format

````

[Today's Date]

*Changes*
- These are changes based on git logs

*Know Issues*
- List of tickets ordered by priority


```

*Installation*

** Local **

Assuming you are doing this on the repo you plan to generate the changelog on

```shell

npm install https://github.com/mechastorm/changelog-gen/tarball/master

```

** Global **

```shell

sudo npm -g install https://github.com/mechastorm/changelog-gen/tarball/master

```

*Usage*

1. Generate a config called "changelog-gen.json"

```json

{
    "tracker"   : "jira",
    "jira"      : {
        "projectKey"    : "JIRAPROJECTKEY",
        "host"          : "project.atlassian.net",
        "searchString"  : "project = JIRAPROJECTKEY AND resolution = Unresolved ORDER BY priority DESC, key DESC", // JQL
        "maxIssuePriorities" : 2
    },
    "ignoreMerges" : true
}

```

2. Run the command

```shell

# If you installed globally
changelog-gen [git-commit-id-or-tag]

# If you installed locally
node node_modules/changelog-gen/bin/changelog-gen [git-commit-id-or-tag]

```