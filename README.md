# StackHawk Shared Configurations

This repo contains configuration snippets, custom scripts, and other resources useful for configuring HawkScan in a modular way.

Say you have a Git repo for an application, and you want to scan it with StackHawk. You would add a StackHawk configuration file and any custom scripts to that repo to make them available to app developers and CI/CD automation.

To simplify configuration and maintenance, you can add this repo as a submodule of your application repo. Then, all of the relatively standard authentication scripts and configuration snippets can be used to enhance the scan configuration.

If you have a lot of apps, you can add this repo as a submodule of all of those application's repos as well. This helps keep your StackHawk configurations DRY (Don't Repeat Yourself) across many repositories, instead of maintaining lots of copies of the same configs and scripts everywhere.

## Recommended Use

 * Add this repo as a submodule of your application's repo[s]
   * `git submodule add git@github.com:zconger/stackhawk-configs.git`
 * Refer to the cnofiguration files when running `hawk scan <config-files>`
