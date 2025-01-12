# Installing and Configuring Grafana using Ansible

This guide provides a step-by-step explanation of how to use an Ansible playbook to install Grafana Enterprise, configure it, and access it via a web browser. Screenshots should be added for each step to enhance clarity.

---

## Prerequisites

- A RHEL-based server (minimal installation recommended).
- Ansible installed on the control node.
- Target hosts listed in your Ansible inventory file under the `database` group.

---

## Ansible Playbook Overview

The provided Ansible playbook performs the following tasks:

1. Downloads the GPG key for Grafana.
2. Imports the GPG key.
3. Creates the Grafana YUM repository configuration file.
4. Installs the latest version of Grafana Enterprise.
5. Starts and enables the Grafana service.
6. Adding default grafana port to firewall

## Steps to Access and Configure Grafana

### 1. Access Grafana via Web Browser

1. Open your browser and navigate to:
   ```
   http://<your-server-ip>:3000
   ```
2. You will see the Grafana login screen.
   - Default credentials:
     - Username: `admin`
     - Password: `admin`
     
![Alt text](https://github.com/user-attachments/assets/87b14cca-68ae-4726-bb2d-a08ec4fcc5b8)


### 2. Change the Default Password

1. After logging in, you will be prompted to change the default password.
2. Enter the new password and confirm it.

![Alt text](https://github.com/user-attachments/assets/d5604982-c0b9-4368-94bb-180fa9e4b017)

### 3. Add Prometheus as a Data Source

1. From the left-hand menu, select **Configuration > Data Sources**.
2. Click **Add data source** and choose **Prometheus**.
3. Enter the URL of your Prometheus server (e.g., `http://<prometheus-ip>:9090`).
4. Click **Save & Test** to verify the connection.

### 4. Import a Dashboard

1. From the left-hand menu, select **Dashboard > New > Import**.
![Alt text](https://github.com/user-attachments/assets/17bce4a1-a60c-4f3f-9433-986da28fec5c)

2. Enter a dashboard ID (e.g., `1860` for a popular Prometheus-Grafana dashboard) or upload a JSON file. Click **Load**
![Alt text](https://github.com/user-attachments/assets/f4615141-0eed-49fb-8db3-343be966e7d6)

3. Review the settings, and click **Import**.
![Alt text](https://github.com/user-attachments/assets/9c92fe4c-74e3-4be5-9bb8-19dc9dd15970)

💥 Now Booom!! You got your first monitoring interface 
![Alt text](https://github.com/user-attachments/assets/7fdd7f25-35c8-4ad3-a8d2-16e979490894)