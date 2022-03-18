# Group by
- having은 무조건 group by 바로 뒤에 !!
```SQL
SELECT NAME, COUNT(NAME) AS COUNT
FROM TEMP_TABLE
GROUP BY NAME
HAVING COUNT > 1
ORDER BY NAME
```
```SQL
-- 틀림
SELECT NAME, COUNT(NAME) AS COUNT
FROM TEMP_TABLE
GROUP BY NAME
ORDER BY NAME
HAVING COUNT > 1
```


# 변수
- 선언
```sql
SET @CNT = -1
```
- for 문
```SQL
SET @CNT = -1

SELECT (@CNT := @CNT + 1)
WHERE @CNT < 10
-- 0 부터 '10'까지 출력됨
```

# if문
- case when 조건 then 실행 else 실행 end
```sql
SELECT NAME,
    CASE WHEN AGE > 10 THEN 'OLD' ELSE AGE END,
    SEX
FROM TMP_TABLE
```