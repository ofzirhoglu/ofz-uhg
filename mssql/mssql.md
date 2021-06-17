# MsSQL

# Data manipülasyon komutları

Data manipülasyon komutları SELECT, INSER, UPDATE, DALETE ve TRUNCATE komutlarını içermektedir.

## SELECT kullanımı

```sql
SELECT
		*
FROM
		CUSTOMERS
```

```sql
SELECT
			ID,
			CUSTOMERNAME,
			CITY,
			[FATHERS NAME]
FROM
			CUSTOMERS
```

## INSERT kullanımı

```sql
INSERT INTO CUSTOMERS
			(
				[CUSTOMERNAME],
				[CITY],
				[BIRTHDATE],
				[DISTRICT],
				[GENDER],
				[FATHERS NAME]
			)
VALUES
			(
				'OSMAN',
				'TRABZON',
				'1970-07-12',
				'AKÇABAT',
				'E',
				'DURSUN'
			)
```

## UPDATE kullanımı

```sql
UPDATE CUSTOMERS
SET
	NATION='US'
```

```sql
UPDATE CUSTOMERS
SET
	NATION='TR',
	AGE=35
```

```sql
UPDATE CUSTOMERS
SET
	NATION='FR',
	-- Yaşları hesaplayarak güncelliyor
	AGE=DATEDIFF(YEAR,BIRTHDATE,GETDATE())
```

```sql
DELETE
FROM
	CUSTOMERS
```

## DELETE kullanımı

```sql
DELETE
FROM
			CUSTOMERS
WHERE
			ID = 4
```

## TRUNCATE kullanımı

```sql
-- Tabloyu sıfırlayarak siler
TRUNCATE TABLE CUSTOMERS
```

## WHERE kullanımı

```sql
SELECT * FROM USERS
WHERE
			ID = 1
```

```sql
SELECT * FROM USERS
WHERE
			GENDER <> 'K'
```

```sql
SELECT * FROM USERS
WHERE
			BIRTHDATE > '19930121'
```

```sql
SELECT * FROM USERS
WHERE
			BIRTHDATE >= '19930121'
```

```sql
SELECT * FROM USERS
WHERE
			BIRTHDATE < '19930121'
```

```sql
SELECT * FROM USERS
WHERE
			BIRTHDATE <= '19930121'
```

```sql
SELECT * FROM USERS
WHERE
			BIRTHDATE BETWEEN '19511229' AND '19930121'
```

```sql
SELECT * FROM USERS
WHERE
			NAMESURNAME LIKE 'ALİ%'
```

```sql
SELECT * FROM USERS
WHERE
			NAMESURNAME NOT LIKE '%UR'
```

```sql
SELECT * FROM USERS
WHERE
			TELNR1 LIKE '%)724%'
```

```sql
SELECT * FROM USERS
WHERE
			BIRTHDATE IN ('19401230','19720225')
```

```sql
SELECT * FROM USERS
WHERE
			BIRTHDATE NOT IN ('19401230','19720225')
```

## AND ve OR kullanımı

```sql
SELECT * FROM CUSTOMERS
WHERE 
			CITY = 'İSTANBUL' AND DISTRICT = 'PENDİK'
```

```sql
SELECT * FROM CUSTOMERS
WHERE 
			CITY = 'İSTANBUL' OR DISTRICT = 'PENDİK'
```

```sql
SELECT * FROM CUSTOMERS
WHERE
			(CITY = 'İSTANBUL' AND DISTRICT = 'PENDİK')
	AND
			(GENDER = 'E' OR NATION = 'TR')
```

```sql
SELECT * FROM CUSTOMERS
WHERE
			(CITY = 'İSTANBUL' AND DISTRICT = 'BORNOVA')
	OR
			(GENDER = 'E' OR NATION = 'TR')
```

## DISTINCT kullanımı

```sql
SELECT DISTINCT
			CITY
FROM
			CUSTOMERS
```

```sql
SELECT DISTINCT
			CITY, DISTRICT
FROM
			CUSTOMERS
```

```sql
SELECT DISTINCT
			CITY, DISTRICT
FROM
			CUSTOMERS
WHERE
			CITY = 'İSTANBUL'
```

## ORDER BY kullanımı

```sql
SELECT *
FROM
			USERS
ORDER BY
			BIRTHDATE --DEFAULT ASC
```

```sql
SELECT *
FROM
			USERS
ORDER BY
			BIRTHDATE DESC
```

```sql
SELECT *
FROM
			USERS
ORDER BY
			BIRTHDATE, --DEFAULT ASC
			NAMESURNAME --DEFAULT ASC
```

```sql
SELECT *
FROM
			USERS
ORDER BY 
		BIRTHDATE DESC, 
		NAMESURNAME DESC
```

```sql
SELECT *
FROM
			USERS
ORDER BY 
			BIRTHDATE ASC, 
			NAMESURNAME DESC
```

```sql
SELECT *
FROM
			USERS
WHERE 
			BIRTHDATE >= '19700101'
ORDER BY
			BIRTHDATE ASC,
			NAMESURNAME DESC
```

```sql
SELECT *
FROM
			USERS
WHERE 
			BIRTHDATE >= '19700101'
ORDER BY
			7 ASC, -- Kolon sıra numarasına göre 7 BIRTHDATE alanı
			5 DESC -- Kolon sıra numarasına göre 5 NAMESURNAME alanı
```

## TOP kullanımı

```sql
SELECT TOP 100 *
FROM
			USERS
```

```sql
SELECT TOP 100 PERCENT *
FROM
			USERS
```
