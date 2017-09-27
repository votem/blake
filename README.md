# Blake (BackLog Analysis KEeper)

Blake is a Slack bot for providing lists of JIRA tickets (e.g. ungroomed backlog
items) to Slack. It will post a list of ticket links to a Slack channel based on
a saved JIRA filter.

A number of configuration options are available via environment variable;
see [`env/example.env`](env/example.env) for more information.

## Prerequisites

*   Node.js (tested with version 6 but others should work)
*   Administrative access to a Slack workspace for configuration
*   A JIRA account with access permissions to the desired filter
*   Docker (optional)

## Setup

To use Blake a bot must first be configured in your Slack workspace. More
information on setting up Slack bots can be found [here](https://api.slack.com/bot-users).

Once that is complete, create a new environment file by coping the example
in the `env` folder. Add the generated token to it, and configure the other
values as appropriate. Note that the bot must be invited to the desired posting
channel with `/invite @blake` (assuming you named your bot `blake` in Slack,
which you should; add a nice avatar of your favorite Blake while you're at it)

Finally run `npm i` to install Node.js dependencies.

## Usage

To run the bot once, execute `. env/your.env && npm start`. It will run the
filter query, post the results, and then exit.

A `Dockerfile` is also provided. Execute `docker build -t blake .` to build the
image, and then run it with `docker run --env-file env/your.env blake`.

## Credits

This software was developed as an internal project at Everyone Counts, Inc.

Everyone Counts provides elegantly simple software and exceptional services to upgrade
the election process. The eLect brand offers unrivaled web-based voting products including
Voter Registration, Online Voting, and Remote Accessible Voting. The product suite
is designed to address pain points facing election officials today, including security,
accessibility, cost, and sustainability.

For more information, visit http://everyonecounts.com.
