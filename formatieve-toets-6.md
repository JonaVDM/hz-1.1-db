## 1

```sql
CREATE TABLE LEVERANCIER (
	ICode integer NOT NULL,
	naam varchar(50) NOT null,
	website varchar(40) NOT NULL,

	CONSTRAINT pk_code PRIMARY KEY (ICode)
);
```

## 2

```sql
INSERT INTO LEVERANCIER VALUES (1, 'Leverancier 01', 'https://leverancier01.nl');
INSERT INTO LEVERANCIER VALUES (2, 'Leverancier 02', 'https://leverancier02.nl');
INSERT INTO LEVERANCIER VALUES (3, 'Leverancier 03', 'https://leverancier03.nl');
```

## 3

```sql
ALTER TABLE ARTIKEL
	ADD ICode int;

ALTER TABLE ARTIKEL
	ADD FOREIGN KEY (ICode)
	REFERENCES LEVERANCIER(ICode);
```

## 4

```sql
CREATE USER Joop PASSWORD 'secret';
CREATE USER Jaap PASSWORD 'secret';
```

## 5

```sql
CREATE ROLE rVerkoop;

GRANT SELECT, UPDATE, INSERT, DELETE ON LEVERANCIER TO rVerkoop;

GRANT rVerkoop TO Jaap;
GRANT rVerkoop TO Joop;
```

##

```sql
create user Barbara password 'secret';

create view vregel
as select ... from bestelregel
where kortings.. = 0
with check option;

grant select on vregel to barabara;
```
