Instituto Superior Técnico, Universidade de Lisboa

**Network and Computer Security**

# Lab guide: SQL Injection Attack Lab (SQLi)

## Goals

- Learn how to detect the presence of a SQL Injection vulnerability.
- Learn how to exploit a SQL Injection vulnerability (`SELECT` and `UPDATE` statements).
- Learn the existing techniques to protect systems against SQL Injections (prepared statements).

## Introduction

For this lab we propose the SQLi Attack Lab that is part of the [SEED Labs Project](https://seedsecuritylabs.org/).

Refer to the [lab webpage (SQLi)](https://seedsecuritylabs.org/Labs_16.04/Web/Web_SQL_Injection/) for full details.
In the end of this lab session you should be able to complete Tasks 1 to 4 of SQL Injection.

Needed Files (1):

- [Description of SEED Labs SQLi lab](https://seedsecuritylabs.org/Labs_16.04/PDF/Web_SQL_Injection.pdf) Tasks 1-4

Follow the document above but try to solve the challenges by yourself. Be inquisitive. Ask yourself why is it working and if there are other methods/solutions to achieve the same results. When you are stuck, check below if we have any tip to help you out.

## Setup

- How do I know which PHP version I am running? Run `php -v`
- The MySQL Reference Manual can be found [here](https://dev.mysql.com/doc/refman/5.7/en/) (check the exact version running using `mysql --version`)
- The address of the vulnerable site is `http://www.SEEDLabSQLInjection.com` (local to the VM).
- Instructions on how to setup the lab environment are [here](https://github.com/tecnico-sec/Setup).

## Tips

### Task 2.1: SQL Injection Attack from webpage (Attacks on SELECT)

- Can you also perform the injection in the `password` field? Check the running `php` file in `/var/www/SQLInjection/unsafe_home.php`.

### Task 2.2: SQL Injection Attack from command line

- Do not forget that you have to encode the non-alphanumeric characters with their `%xx` hexadecimal code.
- In Firefox, using `Web Developer/Network` you can right click on any request and select `Copy as cURL`.

### Task 2.3: Append a new SQL statement

- Can you do it? If you cannot, what do you think is the problem?

### Task 3.1: Modify your own salary (Attacks on UPDATE)

- How can you change your salary? The available query does not allow it. Or does it?
- Do not forget the URL-encodings.

### Task 3.2: Modify other people's salary (Attacks on UPDATE)

- Bob has been slacking around to much. Let us change his salary to 1.
- Can you do it? The available query only allows one to change values for the current user. Really?

### Task 3.3: Modify other people's password (Attacks on UPDATE)

- Why is the injection not working?
- Is it working? Can you login (as `boby`) with the new password? Why or why not?
- Once I heard about something called `sha1sum`.

### Task 4: Countermeasure — Prepared Statement

- Change `unsafe_home.php` and `unsafe_edit_backend.php` files accordingly.
  - `/var/www/SQLInjection/unsafe_home.php`
  - `/var/www/SQLInjection/unsafe_edit_backend.php`
- Do your attacks work after this fix?

**Acknowledgments**

Original version: Pedro Adão

Revisions: Nuno Sabino

----

[SIRS Faculty](mailto:meic-sirs@disciplinas.tecnico.ulisboa.pt)
