# SELECT

`SELECT * FROM users;`  
* `SELECT` veritabanından bilgi almak istediğimizi
* `*` tabloda ki tüm sütünları görmek istediğimizi
* `FROM users` ise adı üstünde users tablosundan bilgileri almak istediğimi
* `;` noktalı virgül ise sorgunun sonu olduğu bildirir.

`SELECT username,password FROM users;`

burada ise tablodaki bütün sutünları değil sadece `username` ve `password` sütünlarını almak istediğimizi söylüyoruz.

---
# WHERE

```
SELECT * FROM users WHERE username='user3';
```

* istenilen user3 verisini tablodan verdi

| id | username  | password   |
|----|-----------|------------|
| 3  | user3     | mypass789  |

```
SELECT * FROM users WHERE username !='user2';
```

* user2 ye eşit olmayan değerleri verdi

| id | username  | password   |
|----|-----------|------------|
| 1  | user1     | pass123    |
| 3  | user3     | mypass789  |
| 4  | user4     | secure321  |
| 5  | user5     | access777  |

## LIKE

```
SELECT * FROM users WHERE username LIKE 'a%'; username sutünunda 'a' harfi ile başlayan verileri verir.

SELECT * FROM users WHERE username LIKE '%n'; username sutünunda 'n' harfi ile biten verileri verir.

SELECT * FROM users WHERE username LIKE '%mi%'; username sutünunda içinde 'mi' geçen verileri verir.
```

# LIMIT 

| id | username  | password   |
|----|-----------|------------|
| 1  | user1     | pass123    |
| 2  | user2     | secret456  |
| 3  | user3     | mypass789  |
| 4  | user4     | secure321  |
| 5  | user5     | access777  |

```
SELECT username, password FROM users LIMIT 1;
```

| username  | password   |
|-----------|------------|
| user1     | pass123    |

```
SELECT username, password FROM users LIMIT 2;
```

| username  | password   |
|-----------|------------|
| user1     | pass123    |
| user2     | secret456  |

```
SELECT username, password FROM users LIMIT 1,1;
```

| username  | password   |
|-----------|------------|
| user2     | secret456  |

```
SELECT username, password FROM users LIMIT 1,2;
```

| username  | password   |
|-----------|------------|
| user2     | secret456  |
| user3     | mypass789  |

```
SELECT username, password FROM users LIMIT 2,1;
```

| username  | password   |
|-----------|------------|
| user3     | mypass789  |

```
SELECT username, password FROM users LIMIT 2,2;
```

| username  | password   |
|-----------|------------|
| user3     | mypass789  |
| user4     | secure321  |

---

## DISTINCT

-- customers tablosunu oluşturalım
```
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    customer_name VARCHAR(50),
    city VARCHAR(50)
);
```
-- customers tablosuna veri ekleyelim
```
INSERT INTO customers VALUES (1, 'John Doe', 'New York');
INSERT INTO customers VALUES (2, 'Jane Smith', 'Los Angeles');
INSERT INTO customers VALUES (3, 'Bob Johnson', 'New York');
INSERT INTO customers VALUES (4, 'Alice Brown', 'Chicago');
INSERT INTO customers VALUES (5, 'Charlie Wilson', 'Los Angeles');

```
Eğer tüm şehirleri listeleyen bir sorgu yaparsanız:

-- Tüm şehirleri listeleyen sorgu
```
SELECT city FROM customers;
```
Sonuç şu olacaktır:
```
Copy code
New York
Los Angeles
New York
Chicago
Los Angeles
```
Ancak, eğer yalnızca benzersiz şehirleri elde etmek istiyorsanız, "**DISTINCT**" kullanabilirsiniz:

-- Yalnızca benzersiz şehirleri listeleyen sorgu
```
SELECT DISTINCT city FROM customers;
```
Bu sorgu, yinelenen şehirleri kaldırır ve yalnızca benzersiz şehirleri getirir:
```
New York
Los Angeles
Chicago
```
# UNION

tabloları birleştimek için kullanılır ....

---

# INSERT

Yeni bir kayıt eklemek için kullanılır. Genel olarak, `INSERT INTO` ifadesiyle birlikte kullanılır.


`INSERT INTO users (username, password, email) VALUES ('newuser', 'newpassword', 'newuser@example.com');`

# UPDATE

## DELETE
