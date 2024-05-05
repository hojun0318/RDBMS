### 데이터 추가
```
mysql＞INSERT INTO {테이블 명}
    -＞ VALUES(1, '또준', '2000-01-01', 'M', 'DEV_BACK', 10000000, null);
```
* 테이블을 정의할 때의 Attribute를 정의한 순서대로 데이터를 채워줘야 한다. 또, 이 값은 모든 Attribute에 대응하는 값을 넣어줘야 한다.
```
mysql＞INSERT INTO {테이블 명} (name, birth_date, sex, position, id)
    -＞ VALUES('유진', '2000-11-11', 'F', 'DEV_BACK', 3);
```
* Attribute name을 적어주면 데이터 입력에 자유도가 생김, 아무튼 위 쿼리는 5개의 Attribute에 대한 값 넣겠다는 의미

### INSERT statement
- INSERT INTO tabe_name VALUES (comma-separated all values);
- INSERT INTO table_name (attribute list)VALUES(attributes list 순서와 동일하게 comma-sseparated values);
- INSERT INTO table_name VALUES (..., ..., ..., ..., ...);

### 데이터 수정
```
mysql＞UPDATE {테이블 명} SET dept_id = 1004 WHERE id = 1;
```
```
mysql＞UPDATE {테이블 명}
    -＞ SET salary = salary * 2
    -＞ WHERE dept_id = 1004;
```
```
mysql＞UPDATE {테이블 1}, {테이블 2}
    -＞ SET salary = salary * 2
    -＞ WHERE id = empl_id and proj_id = 2004;
```
```
mysql＞UPDATE {테이블 1}, {테이블 2}
    -＞ SET salary = salary * 2
    -＞ WHERE {테이블 1}.id = {테이블 2}.empl_id and proj_id = 2004;
```

### UPDATE statement
- UPDATE table_name(s) SET attribute = value[, attribute = vale, ...] [WHERE condition(s)]

### 데이터 삭제
```
mysql＞DELETE FROM {테이블 명} WHERE id = 8;
```
```
mysql＞DELETE FROM {테이블 명} WHERE impl_id= 2;
```
```
mysql＞DELETE FROM {테이블 명} WHERE impl_id = 5 and proj_id = 2003;

mysql＞DELETE FROM {테이블 명} WHERE impl_id = 5 and proj_id <> 2004;
```
```
mysql＞DELETE FROM {테이블 명}
```
* WHERE 절이 없다는 게 특징, 없기 때문에 테이블에 있는 모든 Tuple이 삭제가 된다.
  - UPDATE문 DELETE문 모두 WHERE절 없이도 동작할 수 있는데 모든 데이터를 바꾸거나 모든 데이터를 삭제하게 된다. (대단히 조심스럽게 사용해야 한다.)

### DELETE statement
- DELETE FROM table_name [WHERE condition(s)];