# SQL

`SELECT * FROM users;`  
* `SELECT` veritabanından bilgi almak istediğimizi
* `*` tabloda ki tüm sütünları görmek istediğimizi
* `FROM users` ise adı üstünde users tablosundan bilgileri almak istediğimi
* `;` noktalı virgül ise sorgunun sonu olduğu bildirir.

---

`SELECT username,password FROM users;`

burada ise tablodaki bütün sutünları değil sadece `username` ve `password` sütünlarını almak istediğimizi söylüyoruz.

---

| id | username  | password   |
|----|-----------|------------|
| 1  | user1     | pass123    |
| 2  | user2     | secret456  |
| 3  | user3     | mypass789  |
| 4  | user4     | secure321  |
| 5  | user5     | access777  |


`SELECT username, password FROM users LIMIT 1;` 

| username  | password   |
|-----------|------------|
| user1     | pass123    |


`SELECT username, password FROM users LIMIT 2;`

| username  | password   |
|-----------|------------|
| user1     | pass123    |
| user2     | secret456  |


`SELECT username, password FROM users LIMIT 1,1;`

| username  | password   |
|-----------|------------|
| user2     | secret456  |


`SELECT username, password FROM users LIMIT 1,2;`

| username  | password   |
|-----------|------------|
| user2     | secret456  |
| user3     | mypass789  |


`SELECT username, password FROM users LIMIT 2,1;`

| username  | password   |
|-----------|------------|
| user3     | mypass789  |


`SELECT username, password FROM users LIMIT 2,2;`

| username  | password   |
|-----------|------------|
| user3     | mypass789  |
| user4     | secure321  |

---

`SELECT * FROM users WHERE username='user3';`

//istenilen user3 verisini tablodan verdi

| id | username  | password   |
|----|-----------|------------|
| 3  | user3     | mypass789  |


`SELECT * FROM users WHERE username !='user2';`

// user2 ye eşit olmayan değerleri verdi

| id | username  | password   |
|----|-----------|------------|
| 1  | user1     | pass123    |
| 3  | user3     | mypass789  |
| 4  | user4     | secure321  |
| 5  | user5     | access777  |

