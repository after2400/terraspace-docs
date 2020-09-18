---
title: terraspace log
reference: true
---

## Usage

    terraspace log [ACTION] [STACK]

## Description

The all log command allows you to view multiple logs.

The log commands will filter out the logs for the last ran terraspace command. It does this by filtering for the last found PID in the log files.

## Quick Start

Follow all the logs as you're running `terraspace all up`:

    terraspace log -f

## View Logs

View last 10 lines of each log file.

    terraspace log up network # view up log on specific stack
    terraspace log up         # view all up logs
    terraspace log down       # view all down logs
    terraspace log            # view all logs: up, down, etc

By default, the log command shows the last 10 lines of the logs for each log file. You can use the `-n` option to adjust this.

    terraspace log -n 2       # view last 2 lines of all logs: up, down, etc

To show all logs, use the `-a` option.

    terraspace log up -a

Note, if both an action and stack is specified, then it defaults to showing all logs. If you want to not show all logs in thta case, then you can use `--no-all`.

## Tail Logs

To tail logs, use the `-f` option.

    terraspace log up network -f # view up log on specific stack
    terraspace log up -f         # view all up logs
    terraspace log down -f       # view all down logs
    terraspace log -f            # view all logs: up, down, etc

## Timestamps

The timestamps are shown by default when you are looking for multiple files.  When you specify a both the action and stack for a single log file, then timestamps are not shown.

    terraspace log up         # timestamps will be shown in this case
    terraspace log up network # timestamps not be shown in this case


## Options

```
t, [--timestamps], [--no-timestamps]  # Whether or not to show the leading timestamp. Defaults to timestamps for multiple logs, and no timestamp if a single log is specified. Note: In follow mode, timestamp always shown
f, [--follow], [--no-follow]          # Follow the log in live tail fashion. Must specify a stack if using this option.
n, [--limit=N]                        # Number of lines to limit showing. Only applies in no-follow mode.
                                      # Default: 10
a, [--all], [--no-all]                # All mode turns off the limit. Defaults to all if a single log is specified. Only applies in no-follow mode.
    [--verbose], [--no-verbose]       
    [--noop], [--no-noop]             
```

