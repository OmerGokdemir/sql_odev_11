# sql_odev_11
SQL 11. Ödevi

## Aşağıdaki sorgu senaryolarını *dvdrental* örnek veri tabanı üzerinden gerçekleştiriniz.


1. *actor* ve *customer* tablolarında bulunan *first_name* sütunları için tüm verileri sıralayalım.

```SQL
    (
	SELECT first_name FROM actor
	ORDER BY first_name ASC
    )
    UNION
    (
	SELECT first_name FROM customer
	ORDER BY first_name ASC
    );
```

2. *actor* ve *customer* tablolarında bulunan *first_name* sütunları için kesişen verileri sıralayalım.

```SQL
    (
	SELECT first_name FROM actor
	ORDER BY first_name ASC
    )
    INTERSECT
    (
	SELECT first_name FROM customer
	ORDER BY first_name ASC
    );
```

3. *actor* ve *customer* tablolarında bulunan *first_name* sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.

```SQL
    (
	SELECT first_name FROM actor
	ORDER BY first_name ASC
    )
    EXCEPT
    (
	SELECT first_name FROM customer
	ORDER BY first_name ASC
    );
```

4. İlk 3 sorguyu tekrar eden veriler için de yapalım.

```SQL
    (
	SELECT first_name FROM actor
	ORDER BY first_name ASC
    )
    UNION ALL
    (
	SELECT first_name FROM customer
	ORDER BY first_name ASC
    );
```

### Kesişen öğeler için tekrar eden veriler için ayrıca *ALL* kullanma sonucu değiştirmeyecektir.

```SQL
    (
	SELECT first_name FROM actor
	ORDER BY first_name ASC
    )
    INTERSECT ALL
    (
	SELECT first_name FROM customer
	ORDER BY first_name ASC
    );
```

### Birinci tabloda olan, ikinci tabloda olmayan, tekrar eden veriler için:

```SQL
    (
	SELECT first_name FROM actor
	ORDER BY first_name ASC
    )
    EXCEPT ALL
    (
	SELECT first_name FROM customer
	ORDER BY first_name ASC
    );
```

