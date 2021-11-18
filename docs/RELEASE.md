# Releasing Automation Hub CircleCI Orb

1. Prepare a release PR with the following title **ci: release v{version} [semver:patch/minor/major]** which will contain the changelog information

- **[semver:patch]** will increase the patch version (1.0.0 => 1.0.1)
- **[semver:minor]** will increase the minor version (1.0.0 => 1.1.0)
- **[semver:major]** will increase the major version (1.0.0 => 2.0.0)

2. Squash and merge the PR

_Note: If you want to skip releasing a squashed commit, don't include **[semver:patch/minor/major]** in the commit description_
