# Angle Protocol - Mitigation Review details
- Total Prize Pool: $14,000 USDC 
- [Warden guidelines for C4 mitigation reviews](https://code4rena.notion.site/Guidelines-for-C4-mitigation-reviews-ed10fc5cfbf640bd8dcec66f38b343c4)
- Submit findings [using the C4 form](https://code4rena.com/contests/2023-07-angle-mitigation-review/submit)
- Starts July 17, 2023 20:00 UTC 
- Ends TBD XXX XXX XX 20:00 UTC (ex. `Ends March 30, 2023 20:00 UTC`)

## Important note 

Each warden must submit a mitigation review for *every High and Medium finding* from the parent audit that is listed as in-scope for the mitigation review. **Incomplete mitigation reviews will not be eligible for awards.**

## Findings being mitigated

Mitigations of all High and Medium issues will be considered in-scope and listed here.

- [H-01: Possible reentrancy during redemption/swap](https://github.com/code-423n4/2023-06-angle-findings/issues/24)
- [H-02: The first disputer might lose funds although his dispute is valid.](https://github.com/code-423n4/2023-06-angle-findings/issues/23)
- [H-03: Poor detection of disputed trees allows claiming tokens from a disputed tre](https://github.com/code-423n4/2023-06-angle-findings/issues/10)
- [M-01: LibHelpers.piecewiseLinear will revert when the value is less than the first element of the array](https://github.com/code-423n4/2023-06-angle-findings/issues/40)
- [M-02: Unsafe cast in getCollateralRatio()](https://github.com/code-423n4/2023-06-angle-findings/issues/31)
- [M-03: Read-only reentrancy is possible](https://github.com/code-423n4/2023-06-angle-findings/issues/30)
- [M-04: estimatedAPR() might return the wrong APR.](https://github.com/code-423n4/2023-06-angle-findings/issues/28)
- [M-05: uint128 changeAmount might overflow](https://github.com/code-423n4/2023-06-angle-findings/issues/16)
- [M-06: Interest is not accrued before parameters are updated in SavingsVest](https://github.com/code-423n4/2023-06-angle-findings/issues/13)
- [M-07: User may get less tokens than expected when collateral list order changes](https://github.com/code-423n4/2023-06-angle-findings/issues/8)

[ ⭐️ SPONSORS ADD INFO HERE ]

## Overview of changes

Please provide context about the mitigations that were applied if applicable and identify any areas of specific concern.

## Mitigations to be reviewed

### Branch
[ ⭐️ SPONSORS ADD A LINK TO THE BRANCH IN YOUR REPO CONTAINING ALL PRS ]

### Individual PRs
[ ⭐️ SPONSORS ADD ALL RELEVANT PRs TO THE TABLE BELOW:]

Wherever possible, mitigations should be provided in separate pull requests, one per issue. If that is not possible (e.g. because several audit findings stem from the same core problem), then please link the PR to all relevant issues in your findings repo. 

| URL | Mitigation of | Purpose | 
| ----------- | ------------- | ----------- |
| https://github.com/your-repo/sample-contracts/pull/XXX | H-01 | This mitigation does XYZ | 

## Out of Scope

Please list any High and Medium issues that were judged as valid but you have chosen not to fix.
