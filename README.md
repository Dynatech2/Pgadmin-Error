# Pgadmin-Error
![Screenshot 2024-09-10 151041](https://github.com/user-attachments/assets/234e2265-5488-4ce8-bd65-8a1ed5fb74a7)
# Steps to resolve
### Step 1) Check if PostgreSQL is running:
  - Run the following command to ensure PostgreSQL is running:
    ```
    sudo systemctl status postgresql
    ```
  - If it's not running, you can start it with :
    ```
    sudo systemctl start postgresql
    ```
### Step 2) Check PostgreSQL configuration:
  - Open the postgresql.conf file and verify that PostgreSQL is configured to accept connections on all interfaces (0.0.0.0):
    ```
    sudo nano /etc/postgresql/<version>/main/postgresql.conf
    ```
    - Look for the line or like the box below :
    ```
    listen_addresses = 'localhost'
    ```
    ![Screenshot 2024-09-30 115731](https://github.com/user-attachments/assets/eadf170b-07fa-4df3-8f7e-c9f38d3871d3)

    
