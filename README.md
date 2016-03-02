ETL Rest Server
===============

An ETL Rest Server used by the good people at [AMPATH](https://github.com/ampath/).

Building
--------

    docker build -t etl .

Running
-------

### Step 1. Start a MySQL container

    docker run -d --name mysql4etl -e MYSQL_ROOT_PASSWORD=supersecret \
      -e MYSQL_USER=etl_user -e MYSQL_PASSWORD=etl_password mysql

### Step 2. Run ETL server

    docker run -d --name etl --link mysql4etl:db -p 8002:8002 etl

### Step 3. Profit

    curl https://docker:8002