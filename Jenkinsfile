pipeline {
  agent none
  stages {
    stage('Test') {
      agent {
        docker { image 'node:16-alpine' }
      }
      steps {
        sh 'node --version'
      }
    }
    stage('DB') {
      agent {
        docker { image 'mysql:latest' }
      }
      steps {
        sh 'CREATE database db1;'
        sh 'use db1;'
        sh 'CREATE TABLE customers(id int(10), name varchar(50), city varchar(50),PRIMARY KEY (id ));'
        sh 'insert into customers values(101,'Aishu','Nagpur');'
        sh 'SELECT * from customers;'
      }
    }
  }
}
