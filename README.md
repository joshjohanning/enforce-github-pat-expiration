# enforce-github-pat-expiration

> **Note**
> This action will only work in organizations that have configured SAML SSO.

## Sample Usage

```yml
- name: Check and Revoke PATs
  uses: joshjohanning/enforce-github-pat-expiration@v1
  with:
    organization: ${{ github.repository_owner }}
    policy-in-days: 90
    github-token: ${{ secrets.ORG_ADMIN_TOKEN }}
    dry-run: false # change to true to not revoke any PATs
    create-issue: false # change to true to create an issue and assign to the user whose PAT is being revoked
    issue-repo: ${{ github.repository }} # if create-issue is true, repo to create the issue in
```
