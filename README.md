# GitHub Action Workflow Results to Slack

### Send data into Slack using this [GitHub Action](https://github.com/features/actions) and Slack App!

![image info](/images/template.png)

This package sends data via a Slack app to post to a specific channel using predefined payload (Slack Bitbucket cloud style).

> Bot token is needed!

For additional information see [here](https://github.com/slackapi/slack-github-action#setup-1)!

## Usage
Add this Action as a [step](https://docs.github.com/en/actions/learn-github-actions/workflow-syntax-for-github-actions#jobsjob_idsteps) to your project's GitHub Action Workflow file:

```yaml
- name: Workflow notification to a Slack channel
  id: wf-to-slack
  uses: inetstudio/github-to-slack-action@v1.0
  with:
    # Slack channel id, channel name, or user id to post message.
    channel-id: 'CHANNEL_ID'
    # Secret App token from OAuth & Permissions page
    bot-token: 'BOT_TOKEN'
  env:
    FAILED_RUN: ${{ contains(needs.*.result, 'failure') }}
```

> ❗️ You need to
> fill [`needs:`](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idneeds)
> in this step, action will get a workflow status from selected steps.

## License
The scripts and documentation in this project are released under the [MIT License](https://github.com/inetstudio/github-to-slack-action/blob/master/LICENSE)