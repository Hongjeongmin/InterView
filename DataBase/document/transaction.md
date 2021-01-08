# 트랜잭션(Transaction)
트랜잭션은 데이터베이스의 상태를 변화시키는 하나의 논리적 기능을 수행하기 위한 작업의 단위 또는 한꺼번에 모두 수행되어야할 일련의 연산들을 의미한다.

## 트랜잭션 특징
- 트랜잭션은 데이터베이스 시스템에서 병행 제어 및 회복 작업 시 처리되는 작업의 논리적 단위이다.
- 사용자가 시스템에 대한 서비스 요구 시 시스템이 응답하기 위한 상태 변화 과정의 작업단위이다.
- 하나의 트랜잭션은 Commit되거나 Rollback 된다.

# ACID
## Atomicity(원자성)
1. 트랜잭션의 연산은 데이터베이스에 모두 반영되거나 반영되면 안된다.
2. 트랜잭션 내의 모든 명령은 반드시 완벽히 수행되어야 하며, 모두 완벽히 수행되지 않고 어느하나라도 오류가 발생하면 트랜잭션 전부가 취소되어야 한다.

## Consistency(일관성)
1. 트랜잭션이 작업의 실행을 성공적으로 완료하면 언제나 일관성 있는 데이터베이스 상태로 변화해야한다.
2. 시스템이 가지고 있는 고정요소는 트랜잭션 수행 전과 트랜잭션 수행 완료 후의 상태가 같아야 한다.
    - ex) 데이터타입이 Integer인 속성이 String 타입으로 변경되면 안된다.

## Isolation(격리성)
1. 트랜잭션 수행시 다른 트랜잭션의 작업이 끼어들지 못하도록 보장하는 것을 말한다.
2. 즉, 트랜잭션끼리는 서로를 간섭할 수 없다. (간섭가능 범위를 [isolationLevel](../document/isolationLevel.md)이라고 한다.)

## 지속성(Durability)
1. 성공적으로 수행된 트랜잭션은 DataBase(HardDisk)에 영원히 반영이 되는 것을 말합니다.
2. commit을 하면 현재 상태는 영원히 보장됩니다.