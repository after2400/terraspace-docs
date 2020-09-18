---
title: terraspace cloud sync
reference: true
---

## Usage

    terraspace cloud sync [STACK]

## Description

sync workspace

## Example

    $ terraspace cloud sync
    About to sync these project stacks with Terraform Cloud workspaces:

        Stack => Workspace
        demo => demo-dev-us-west-2
        demo2 => demo2-dev-us-west-2

    A sync does the following for each workspace:

      1. Create or update workspace, including the VCS settings.
      2. Set the working dir.
      3. Set env and terraform variables.

    Are you sure? (y/N) y
    Syncing to Terraform Cloud: demo => demo-dev-us-west-2
    Syncing to Terraform Cloud: demo2 => demo2-dev-us-west-2
    $


## Options

```
y, [--yes], [--no-yes]  # bypass are you sure prompt
```

