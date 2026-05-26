# scnmnt-quota-service — reusability notes

**Type:** `subsystem`

## What the consumer must change to use this elsewhere

The `DefaultPath` constant (`data/quota.db`) specifies the local bbolt database file path. `DailyGrant` (10) and `BalanceCap` (100) are hardcoded constants defining the quota policy. Error messages like '浏览器指纹不正确' are hardcoded in Chinese and would need localization or generalization. The use of `bbolt` is a specific technology choice.

## Invariants you must not break

- User balances must not exceed `BalanceCap`.
- Daily grants must only apply once per day per user.
- Credits must be accurately deducted upon successful 'Spend' operations.
