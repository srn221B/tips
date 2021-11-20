## Commands
1. brew install gnu-getopt coreutils
2. export PATH="/usr/local/opt/gnu-getopt/bin":$PATH
3. git clone https://github.com/apache/airflow.git
4. cd airflow
5. ./breeze start-airflow

## Tips
- execute db shell
  - `airflow-db shell`
- create user
  - `airflow users create -u username -f firstname -l lastname -r Admin -e email
  - https://airflow.apache.org/docs/apache-airflow/stable/security/webserver.html 
- reset DB
  - airflow-db reset
- start
  - airflow-scheduler
  - airflow-webserver

## Details
- https://www.youtube.com/watch?v=4MCTXq-oF68&t=389s
