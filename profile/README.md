# g/d/n/a (gdnaio)

Org-wide GitHub defaults live here.

## Reusable workflows
- `.github/workflows/dependabot-sweep.yml` \u2014 action-version drift sweep (Node-runtime deprecation early warning). Call it from any repo:
  ```yaml
  jobs:
    sweep:
      uses: gdnaio/.github/.github/workflows/dependabot-sweep.yml@main
      permissions:
        contents: read
        id-token: write
      with:
        slack_channel: int-ai-gdnainternal-aeos-chat-dev-ops
        aws_role_arn: arn:aws:iam::ACCOUNT_ID:role/your-oidc-role
  ```

## Workflow templates
In any repo: **Actions \u2192 New workflow \u2192** look under the org templates for **"CI Maintenance Sweep"**. Also copy `workflow-templates/dependabot.yml` to your repo's `.github/dependabot.yml` to enable automated action-version bump PRs.
