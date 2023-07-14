# Angle Protocol - Mitigation Review details

- Total Prize Pool: $14,000 USDC
- [Warden guidelines for C4 mitigation reviews](https://code4rena.notion.site/Guidelines-for-C4-mitigation-reviews-ed10fc5cfbf640bd8dcec66f38b343c4)
- Submit findings [using the C4 form](https://code4rena.com/contests/2023-07-angle-mitigation-review/submit)
- Starts July 17, 2023 20:00 UTC
- Ends TBD XXX XXX XX 20:00 UTC (ex. `Ends March 30, 2023 20:00 UTC`)

## Important note

Each warden must submit a mitigation review for _every High and Medium finding_ from the parent audit that is listed as in-scope for the mitigation review. **Incomplete mitigation reviews will not be eligible for awards.**

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

Changes related to High and Medium issues on Merkl can be found [here](https://github.com/AngleProtocol/merkl-contracts/compare/code-423n4-2023-06-angle...code-423n4-2023-06-angle-mitigation).
Changes that we intend to make on Merkl prior to final deployment, so including QA and GAS can be found [here](https://github.com/AngleProtocol/merkl-contracts/compare/code-423n4-2023-06-angle...code-423n4-2023-06-angle-full-mitigation). Updated tests and scripts are on the `main` branch.

Changes related to High and Medium issues on Transmuter can be found [here](https://github.com/AngleProtocol/angle-transmuter/compare/code-423n4-2023-06-angle...code-423n4-2023-06-angle-mitigation).
Changes that we intend to make on Transmuter prior to final deployment, so including QA and GAS can be found can be found [here](https://github.com/AngleProtocol/angle-transmuter/compare/code-423n4-2023-06-angle...code-423n4-2023-06-angle-full-mitigation). Updated tests and scripts are on the `main` branch.

## Mitigations to be reviewed

### Individual PRs

| URL                                                                                               | Mitigation of | Purpose                                             |
| ------------------------------------------------------------------------------------------------- | ------------- | --------------------------------------------------- |
| https://github.com/AngleProtocol/angle-transmuter/commit/864c1c47cb550f8e337244f0f70409a171a4e671 | H-01          | Adds a reentrancy guard to several functions        |
| https://github.com/AngleProtocol/merkl-contracts/commit/7402ee6b84789391479c5876b27be23fd579f7b2  | H-02          | Applies the suggested fix                           |
| https://github.com/AngleProtocol/merkl-contracts/commit/82d8c0ff37b4a9ad8277cac4aef85f3ca0ad5c7c  | H-03          | Applies the suggested fix                           |
| https://github.com/AngleProtocol/angle-transmuter/commit/5f7635cdab52b75416309d45f8cd253609c705ff | M-01          | Add an handler for this edge case                   |
| https://github.com/AngleProtocol/angle-transmuter/commit/6f2ffcb1e89e3bba05c9aa2133ef94347aa42c28 | M-02          | Adds safeCast                                       |
| https://github.com/AngleProtocol/angle-transmuter/commit/864c1c47cb550f8e337244f0f70409a171a4e671 | M-03          | Adds a reentrancy guard to several functions        |
| https://github.com/AngleProtocol/angle-transmuter/commit/337c65d005bbd8ed6dfa76929d2cae475066756a | M-04          | Applies the suggested fix                           |
| https://github.com/AngleProtocol/angle-transmuter/commit/94c4e51ae3400a63532e85f04f4081152adc97db | M-06          | Calls `accrues` before updating sensible parameters |
| https://github.com/AngleProtocol/angle-transmuter/commit/f8d0bf7c4009586f7022d5929359041db3990175 | M-07          | Applies the suggested fix                           |
| https://github.com/AngleProtocol/merkl-contracts/commit/3c2fe3a956cdd29b632e8d7a20e1fc2ce5e8ac37  | QA & GAS      |                                                     |
| https://github.com/AngleProtocol/angle-transmuter/commit/66bba3f5dba4ab6307c997e350dfadb13d2a2119 | QA & GAS      |                                                     |

## Out of Scope

- [M-05: uint128 changeAmount might overflow](https://github.com/code-423n4/2023-06-angle-findings/issues/16): we consider that there is no risk here as swaps will be reverting, and that the chances that this happen are infinitesimals
