# MySQL Installation on Ubuntu

This guide explains how to install and configure MySQL Server on Ubuntu (20.04, 22.04, and 24.04).

---

## Prerequisites

- Ubuntu 20.04 / 22.04 / 24.04
- A user account with `sudo` privileges
- Internet connection

---

## Step 1: Update Package Index

Update the package repository before installing MySQL.

```bash
sudo apt update
```

---

## Step 2: Install MySQL Server

Install the MySQL server package.

```bash
sudo apt install mysql-server -y
```

---

## Step 3: Verify MySQL Installation

Check the status of the MySQL service.

```bash
sudo systemctl status mysql
```

If the service is not running, start and enable it.

```bash
sudo systemctl start mysql
sudo systemctl enable mysql
```

---

## Step 4: Secure MySQL Installation

Run the security script to improve the security of your MySQL installation.

```bash
sudo mysql_secure_installation
```

During the setup, you can:

- Set a root password (if applicable)
- Remove anonymous users
- Disable remote root login
- Remove the test database
- Reload privilege tables

It is recommended to answer **Y** for all security-related prompts.

---

## Step 5: Log in to MySQL

### Using Ubuntu's Default Authentication

```bash
sudo mysql
```

### Using Password Authentication

```bash
mysql -u root -p
```

Enter the root password when prompted.

---

## Step 6: Verify the Installation

Check the installed MySQL version.

### From the Terminal

```bash
mysql --version
```

Example output:

```text
mysql  Ver 8.0.xx for Linux on x86_64
```

### From the MySQL Shell

```sql
SELECT VERSION();
```

---

## Step 7: Create a Database and User (Recommended)

Create a new database.

```sql
CREATE DATABASE mydb;
```

Create a new user.

```sql
CREATE USER 'myuser'@'localhost' IDENTIFIED BY 'StrongPassword123!';
```

Grant privileges.

```sql
GRANT ALL PRIVILEGES ON mydb.* TO 'myuser'@'localhost';
```

Reload privileges.

```sql
FLUSH PRIVILEGES;
```

Exit MySQL.

```sql
EXIT;
```

---

## Useful MySQL Service Commands

### Start MySQL

```bash
sudo systemctl start mysql
```

### Stop MySQL

```bash
sudo systemctl stop mysql
```

### Restart MySQL

```bash
sudo systemctl restart mysql
```

### Check Service Status

```bash
sudo systemctl status mysql
```

---

## Troubleshooting

If you receive the following error:

```text
Package 'mysql-server' has no installation candidate
```

Run the following command to check your Ubuntu version:

```bash
lsb_release -a
```

Then verify your package sources:

```bash
sudo apt update
```

If the issue persists, share:

- Ubuntu version
- Output of `lsb_release -a`
- Complete installation error message

---

## References

- Ubuntu LTS: 20.04, 22.04, 24.04
- MySQL Server 8.x

---

## License

This guide is provided for educational purposes.
