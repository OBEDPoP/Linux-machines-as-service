# **Setup Guide for Memcached, MySQL, Nginx, RabbitMQ, and Tomcat on Linux**

feel free to use the scripts memcache.sh/myql.sh/nginx.... for direct installation
download it to your ubuntu machine -> give permission -> sh /path/file.sh

## **1. Installing and Configuring Memcached**
### **Installation**
```bash
sudo apt update
sudo apt install memcached libmemcached-tools -y
```

### **Configuration**
Edit the Memcached configuration file:
```bash
sudo nano /etc/memcached.conf
```
Modify memory allocation (e.g., 128MB):
```
-m 128
```
Restart the service:
```bash
sudo systemctl restart memcached
sudo systemctl enable memcached
```

### **Verify Installation**
```bash
echo "stats" | nc localhost 11211
```

---

## **2. Installing and Configuring MySQL**
### **Installation**
```bash
sudo apt update
sudo apt install mysql-server -y
```

### **Secure Installation**
```bash
sudo mysql_secure_installation
```

### **Start & Enable MySQL**
```bash
sudo systemctl start mysql
sudo systemctl enable mysql
```

### **Verify Installation**
```bash
mysql -u root -p
```

---

## **3. Installing and Configuring Nginx**
### **Installation**
```bash
sudo apt update
sudo apt install nginx -y
```

### **Start & Enable Nginx**
```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

### **Verify Installation**
```bash
systemctl status nginx
```

### **Configure Firewall (If Enabled)**
```bash
sudo ufw allow 'Nginx Full'
```

---

## **4. Installing and Configuring RabbitMQ**
### **Installation**
```bash
sudo apt update
sudo apt install rabbitmq-server -y
```

### **Start & Enable RabbitMQ**
```bash
sudo systemctl start rabbitmq-server
sudo systemctl enable rabbitmq-server
```

### **Enable RabbitMQ Management Plugin**
```bash
sudo rabbitmq-plugins enable rabbitmq_management
```

### **Check Status**
```bash
sudo rabbitmqctl status
```

---

## **5. Installing and Configuring Tomcat**
### **Installation**
```bash
sudo apt update
sudo apt install tomcat9 tomcat9-admin -y
```

### **Start & Enable Tomcat**
```bash
sudo systemctl start tomcat9
sudo systemctl enable tomcat9
```

### **Verify Installation**
```bash
systemctl status tomcat9
```

### **Access Tomcat Web Interface**
Default URL: [http://localhost:8080](http://localhost:8080)

---

## **Conclusion**
This guide covers the installation and basic configuration of Memcached, MySQL, Nginx, RabbitMQ, and Tomcat on Linux. For additional configurations and security hardening, refer to the official documentation of each service.

