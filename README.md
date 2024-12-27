# ERC20 Balance Calculation Error

This repository demonstrates a common error in ERC20 token contracts: an incorrect balance calculation. The `balanceOf` function fails to account for the total supply, resulting in inaccurate balance reports.

## Bug Description
The `balanceOf` function only retrieves the balance from a local mapping, neglecting to consider the impact of other contract functions (e.g., minting, burning, transferring). This can cause the reported balances to deviate from the actual balances and create security risks.

## Solution
The solution involves correctly calculating the balance by taking the total supply and the transfers, into account, ensuring that the balance reported is accurate.

## How to reproduce the bug
1. Deploy the `bug.sol` contract.
2. Mint some tokens to different accounts.
3. Observe that the `balanceOf` function returns incorrect balances.