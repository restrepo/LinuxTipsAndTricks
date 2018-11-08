# MySQL and MariaDB tips and tricck
## Creates a dump with proper utf8 encoding. See [here](https://makandracards.com/makandra/595-dumping-and-importing-from-to-mysql-in-an-utf-8-safe-way)
* Created dump
```bash
mysqldump --default-character-set=latin1 --opt -u root -p ojs2 -r ojs2.sql
sed -i -e ':a' -e 'N' -e  '$!ba' -e 's|\/\*!40101 SET NAMES latin1 \*\/;\n||' ojs2.sql
```
* Recover dump
```bash
mysql -uroot -p --default-character-set=utf8 $DB < ojs2.sql
```
