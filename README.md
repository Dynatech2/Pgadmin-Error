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

    - Change it to :
    ```
    listen_addresses = '*'
    ```
    ![Screenshot 2024-09-30 120403](https://github.com/user-attachments/assets/57dbb5fa-af3d-4152-9090-700b315d0e2a)
  - Click ctrl+o to save, then press enter and ctrl+x to exit
### Step 3) Update the pg_hba.conf file:
  -Open the pg_hba.conf file and ensure that PostgreSQL allows remote connections:
  ```
  sudo nano /etc/postgresql/<version>/main/pg_hba.conf
  ```
  - Add the following line at the bottom:
  ```
  host    all             all             0.0.0.0/0               md5
  ```
  ![Screenshot 2024-09-30 121851](https://github.com/user-attachments/assets/eef8146b-9ebe-438d-bb6c-aefb763e195e)
  - Click ctrl+o to save, then press enter and ctrl+x to exit

### Step 4) Restart PostgreSQL service: After making changes to the configuration files, restart PostgreSQL:
  ```
  sudo systemctl restart postgresql
  ```
### Step 5) Additional if it doesn't work 
  - https://www.youtube.com/watch?v=LObmSDf9p6Y
