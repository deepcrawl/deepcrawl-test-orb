# Automation Hub CircleCI Orb

[![CircleCI Orb Version](https://badges.circleci.com/orbs/deepcrawl/deepcrawl-test.svg)](https://circleci.com/orbs/registry/orb/deepcrawl/deepcrawl-test) [![GitHub License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/deepcrawl/deepcrawl-test/main/LICENSE) [![CircleCI Community](https://img.shields.io/badge/community-CircleCI%20Discuss-343434.svg)](https://discuss.circleci.com/c/ecosystem/orbs)

`deepcrawl/deepcrawl-test` is exposing the `run-build` job which will run a build on Automation Hub.

## How to use

In order to use Automation Hub CircleCI Orb, you need to:

1. Create a CircleCI context `deepcrawl-test`, which contains the following environment variables:

- `DEEPCRAWL_TEST_USER_KEY_ID`
- `DEEPCRAWL_TEST_USER_KEY_SECRET`

Both environment variables should be set by creating a new API key [here](https://app.deepcrawl.com/dc-api).

2. Setup your CircleCI workflow ([example](https://github.com/deepcrawl/deepcrawl-test-orb/blob/main/src/examples/example.yml)):

```
version: 2.1
orbs:
  deepcrawl-test: deepcrawl/deepcrawl-test@1.0.0
workflows:
  deploy:
    jobs:
      - deepcrawl-test/run-build:
          # Context defined at step 1
          context: deepcrawl-test
          # Test suite ID created in Automation Hub
          testSuiteId: "YOUR_TEST_SUITE_ID"
          # Can be used to make it non-blocking
          startOnly: false
```

_Note: Make sure to run this job after your website is deployed, by using `requires` property of the job._

**For other ways to trigger an Automation Hub Build please see: https://github.com/deepcrawl/deepcrawl-test**
