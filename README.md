# databases
sql and No-sql


# ACID
ACID is a set of properties that ensure the reliable processing of database transactions.
### Transaction
1) A collection of queries.
2)  A transaction ensures that a group of operations either completely succeeds or fails.

## Key Of Transaction

## Atomicity

1) all queries must succeed if one fails all should be rollback.


## Isolation
2) each tranaction it for himseldf forexample db A not intrupt fot transcation B

## Consistency

3) A tranaction must bring the database from one  valid state to another  valid state,
example: a bank has 900$ and in there from account a send 300$ to account b it delete 300 - 9-- but not ++ 300 to data and it is false
less 300 but not add 300 .
or: If a database has a rule that every account must have a positive balance, any transaction that would lead to a negative balance should fail.
## Durability
4) for example you have trancaction and to that moment power out age and we store the data on the dist event that we do that transcaction