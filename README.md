# github-auto-commit

Automated GitHub Action workflow for daily monitoring of commit activity across all associated repositories.

It will auto check all your repositories if there is any new commit today (default is 00:00 - 23:55).

If not, it will auto commit in `dummy.txt` file and push to the repository.

## Features

- [x] Auto commit and push to the repository if there is no commit in your all repos today.
- [x] Support configuration.
- [x] Default is China time zone, you can change by yourself.

## Usage

[![Clone this repo](https://img.shields.io/badge/Clone-This%20Repo-brightgreen.svg)](https://github.com/new?template_name=github-auto-commit&template_owner=dribble-njr&owner=%40me&name=github-auto-commit&description=Make+your+GitHub+green!&visibility=public)

> **Note**: Don't fork this repository, because the GitHub Actions will not work in the forked repository.

1. Generate a new personal access token (`PAT`) with the `repo` scope.
2. In the repository settings.
   1. Find the `Security` tab in the left.
   2. Go to Secrets and variables.
   3. Click Actions.
   4. In this page, click 'New repository secret'.
   5. Add a new secret with the name `TOKEN` and the value of the `PAT` generated in step 2.
   6. You can use another name you want, but you need to change the name `${{ secrets.TOKEN }}` in the file .github/workflows/auto-commit.yml.

## Configuration

You can change the configuration by yourself.

1. Change the scheduling time on `Schedule`, the default is `50 15 * * *` (UTC, every day at 23:50 in China time).
2. Change the `email` and `name` information on `Set up Git` step in .github/workflows/auto-commit.yml.
3. Change `date_today`, `time_start`, `time_end`, and `commit_message` on the last step.
