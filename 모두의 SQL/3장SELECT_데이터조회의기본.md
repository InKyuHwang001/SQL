# 01 SELECT 문의 기본 문법

## 1 SQL 문 작성 규칙

1. 대소문자의 구별이 없다.
2. SQL 문은 한 줄 또는 여러 줄로 작성할 수 있다.
3. 들여쓰기는 SQL 문장을 좀 더 쉽게 함
4. 명령어를 대문자로 하고 나머지를 소문자로 하는 것이 가독성이 좋음


```python
[예제 3-1]

SELECT *
FROM   employees;
---------------------------------------------------

3.1.3

[예제 3-2]

SELECT employee_id, first_name, last_name 
FROM   employees;
---------------------------------------------------

3.1.3

[예제 3-3]

SELECT employee_id, first_name, last_name 
FROM   employees
ORDER BY employee_id DESC;
---------------------------------------------------

3.1.4

SELECT job_id
FROM   employees;
---------------------------------------------------

[예제 3-4]

SELECT DISTINCT job_id
FROM   employees;
---------------------------------------------------

3.1.5

[예제 3-5]

SELECT employee_id AS 사원번호, first_name AS 이름, last_name AS 성
FROM   employees;
---------------------------------------------------

3.1.6

[예제 3-6]

SELECT  employee_id, first_name||last_name
FROM    employees;
---------------------------------------------------

[예제 3-7]

SELECT employee_id, 
       first_name||' '||last_name,
       email||'@'||'company.com'
FROM   employees;
---------------------------------------------------

3.1.7

[예제 3-8]

SELECT employee_id, salary, salary+500, salary-100, (salary*1.1)/2
FROM   employees;
---------------------------------------------------

3.1.7

[예제 3-9]

SELECT employee_id AS 사원번호, 
       salary AS 급여, 
       salary+500 AS 추가급여, 
       salary-100 AS 인하급여, 
       (salary*1.1)/2 AS 조정급여
FROM   employees;
```

## 02 WHERE 조건 절을 활용한 데이터 검색


```python
예제 3-10]

SELECT *
FROM   employees
WHERE  employee_id = 100;
---------------------------------------------------

[예제 3-11]

SELECT *
FROM   employees
WHERE  first_name = 'David';
---------------------------------------------------

[예제 3-12]

SELECT *
FROM   employees
WHERE  employee_id >= 105;
---------------------------------------------------

3.2.2

[예제 3-13]

SELECT *
FROM   employees
WHERE  salary BETWEEN 10000 AND 20000;
---------------------------------------------------

[예제 3-14]

SELECT *
FROM   employees
WHERE  salary IN (10000, 17000, 24000);
---------------------------------------------------

[예제 3-15]

SELECT *
FROM   employees
WHERE  job_id LIKE 'AD%';
---------------------------------------------------

[예제 3-16]

SELECT *
FROM   employees
WHERE  job_id LIKE 'AD___';
---------------------------------------------------

[예제 3-17]

SELECT *
FROM   employees
WHERE  manager_id IS NULL;
---------------------------------------------------

3.2.3

[예제 3-18]

SELECT *
FROM   employees
WHERE  salary > 4000
AND    job_id = 'IT_PROG';
---------------------------------------------------

[예제 3-19]

SELECT *
FROM   employees
WHERE  salary > 4000
AND    job_id = 'IT_PROG'
OR     job_id = 'FI_ACCOUNT';
---------------------------------------------------

[예제 3-20]

SELECT *
FROM   employees
WHERE  employee_id <> 105;
---------------------------------------------------

[예제 3-21]

SELECT *
FROM   employees
WHERE  manager_id IS NOT NULL;
```
