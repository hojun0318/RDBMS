- Domain(SQL: ​Domain) : Set of atomic values
- Domain name
- Attribute(Column) : domain이 relation에서 맡은 역할 이름
- Tuple(Row) : 각 attribute의 값으로 이루어진 리스트, 일부 값은 Null일 수 있다.
- Relation(Table) : set of tuples
- Relation name

---------------------------

- Relation schema
  - relation의 구조를 나타낸다.
  - relation 이름과 attribute 리스트로 표기된다.
  - attribute와 관련된 constraints도 포함된다.
- Degree of relation
  - relation schema에서 attributes의 수
- Relational Database
  - relational data model에 기반하여 구조화된 DB
  - relational database는 여러 개의 relations로 구성된다.
- Relational database schema
  - relation schemas set + integrity constraints set

---------------------------

- Relations's characteristic
  - relation은 중복된 tuple을 가질 수 없다. (relation is set of tuples)
  - relation의 tuple을 식별하기 위해 attribute의 부분 집합을 key로 설정한다.
  - relation에서 tuple의 순서는 중요하지 않다.
  - 하나의 tuple에서 attribute의 순서는 중요하지 않다.
  - attribute는 atomic 해야 한다. (composite or multivalued attribute 허용 안됨)

---------------------------

- Null
  - 값이 존재하지 않는다.
  - 값이 존재하나 아직 그 값이 무엇인지 알지 못한다.
  - 해당 사항과 관련이 없다.

---------------------------

- Keys
  - Super key
    - relation에서 tuples를 unique하게 식별할 수 있는 attributes set
- Candidate key
  - 어느 한 attribute라도 제거하면 unique하게 tuples를 식별할 수 없는 super key
  - key or minimal super key
- Primary key
  - relation에서 tuples를 unique하게 식별하기 위해 선택된 candidate key
- Unique key
  - primary key가 아닌 candidate key
  - alternate key
- Foreign key
  - 다른 relation의 PK를 참조하는 attributes set

---------------------------

- Constraints : relational database의 relations들이 항상 지켜줘야 하는 제약 사항

- Implicit constraints
  - relational data model 자체가 가지는 contraints
  - relation은 중복되는 tuple을 가질 수 없다.
  - relation 내에서는 같은 이름의 attribute를 가질 수 없다.
- Schema-based constraints == explict constraints
  - 주로 DDL을 통해 schema에 직접 명시할 수 있는 constraints
    - Domain contraints
      - attribute의 value는 해당 attribute의 domain에 속한 value여아 한다.
    - Key constraints
      - 서로 다른 tuples는 같은 value의 key를 가질 수 없다.
    - Null value constraint
      - attribute가 NOT NULL로 명시됐다면 NULL을 값으로 가질 수 없다.
    - Entity integrity constraint
      - primary key는 value에 NULL을 가질 수 없다.
    - Referential integrity constraint
      - FK와 PK와 도메인이 같아야 하고 PK에 없는 values를 FK가 값으로 가질 수 없다.