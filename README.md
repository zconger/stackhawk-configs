# StackHawk Shared Configurations

This repo contains configuration snippets, custom scripts, and other resources useful for configuring HawkScan in a modular way.

Say you have a Git repo for an application, and you want to scan it with StackHawk. You would add a StackHawk configuration file and any custom scripts to that repo to make them available to app developers and CI/CD automation.

To simplify configuration and maintenance, you can add this repo as a [submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules) of your application repo. Then, all of the relatively standard authentication scripts and configuration snippets can be used to enhance the scan configuration.

If you have a lot of apps, you can add this repo as a submodule of all of those application's repos as well. This helps keep your StackHawk configurations DRY (Don't Repeat Yourself) across many repositories, instead of maintaining lots of copies of the same configs and scripts everywhere.

## Recommended Use

To use this repo as a submodule of other projects, take the following steps:

 * Add the repo as a submodule to your other project repos
 * Initialize and sync the submodule when using those project repos

 ### Add this repo as a submodule of your application's repo[s]

To add this repo as a submodule of your app repo, check out the app repo, and from within the repo directory, run the following command:
```shell
git submodule add https://github.com/zconger/stackhawk-configs.git
```

This will stage two files to your repo which you should commit and push:

`stackhawk-configs`: The git submodule project directory where the submodule contents are checked out. The contents of the directory are *not* tracked in your app repo, only this directory and some metadata.

`.gitmodules`: A configuration file defining all git submodules tracked in the app repo. This is how the submodule configuration can be used by anyone checking out this app repo in the future.

You can see the staged changes using `git status`:
```shell
zconger@magpie javaspringvulny % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   .gitmodules
        new file:   stackhawk-configs
```

Commit and push these changes to your repo.

```shell
git commit -am "add stackhawk-configs submodule"
git push origin main
```

# 

 
 * Refer to the configuration files when running `hawk scan <config-files>`
