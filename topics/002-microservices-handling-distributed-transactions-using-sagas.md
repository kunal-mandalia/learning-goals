# Saga Pattern

Alternative to Two-Phase Commit.

RDBMS not good choice for distributed transactions, magnitude faster to use NoSQL database which supports atomic updates on a single entity.

Based on a paper written in 1987.

A Saga is a sequence of local transactions and their associated compensating transactions.

While a local transaction (i.e. within the domain of a particular microservice) is a state change which takes another step toward the completion of a series of steps or workflow, a compensating transaction is a state change which semantically rollsback a previous change.

Two implementation strategies:
1. Events/Choreography no central coordinator, each service listens for messages by other services and react accordingly
2. Command/Orchestration: a central coorindator is responsible for the sequence of actions and business logic

## Events / Choreography

### Rollbacks

A service will listen to both successful and failing events of another

## Issues

Atomically updating database and publishing a message together

### Resources
[Couchbase](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)