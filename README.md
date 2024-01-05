# Setting-Up-LAMP-on-AWS-A-Comprehensive-Guide
This guide provides a step-by-step approach to setting up a robust LAMP (Linux, Apache, MySQL, PHP) stack on your Amazon Web Services (AWS) EC2 instance. Each step is explained in detail, emphasizing professional best practices for security and performance.

# LAMP Stack Installation and Configuration

# Step 1: Installing Apache2
This step installs the Apache2 web server on your AWS instance, which will be responsible for serving your web applications.
``` bash
sudo apt install apache2
```
This command uses the package manager (apt) to install Apache2.

# Starting Apache2 web server
``` bash sudo systemctl start apache2 ```
After installation, this command starts the Apache2 web server.


# Checking whether Apache2 is running or not
``` bash sudo systemctl status apache2 ```
This command checks the status of the Apache2 service to ensure it is running without any issues.


# Enable automatic Apache2 start service at boot time
``` bash sudo systemctl enable apache2 ```
This command ensures that Apache2 starts automatically whenever the system boots up.

# Step 2: Installing MySQL Server
This step involves installing MySQL Server, which is a relational database management system.


# Installing MySQL Server
``` bash sudo apt install mysql-server ```
This command installs the MySQL Server package.


# Checking if MySQL Server is running
``` bash sudo systemctl status mysql ```
This command checks the status of the MySQL service to verify that it is running.


# Securing MySQL Installation
``` bash sudo mysql_secure_installation ```
This interactive script guides you through the process of securing your MySQL installation by setting a root password and other security-related configurations.

# Step 3: Installing PHP
This step installs PHP along with necessary packages for integrating it with Apache2 and MySQL.


# Installing PHP with other packages
``` bash sudo apt install php libapache2-mod-php php-mysql ```
This command installs PHP and its modules for Apache2 and MySQL integration.

# Step 4: Configuring PHP
This step configures Apache2 to recognize and process PHP files.


# Configuring Apache2 to use PHP
``` bash sudo nano /etc/apache2/mods-enabled/dir.conf ```
This command opens the Apache2 dir.conf configuration file for editing.

Inside the file, you add index.php to the list of directory index files to ensure that Apache2 prioritizes processing PHP files.

# Step 5: Installing phpMyAdmin
This step installs phpMyAdmin, a web-based administration tool for managing MySQL databases.


# Installing phpMyAdmin
``` bash sudo apt install phpmyadmin ```
This command installs phpMyAdmin.


# Configuring phpMyAdmin with Apache2
``` bash sudo nano /etc/apache2/apache2.conf ```
This command opens the Apache2 apache2.conf configuration file for editing.

Inside the file, you add an Include statement to include the phpMyAdmin configuration.
``` bash Include /etc/phpmyadmin/apache.conf ```
