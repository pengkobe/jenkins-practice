# jenkins-practice

learn how to use jenkins to build and deploy projects

## Official Guide

### Getting started

1. 下载 jenkins.war
2. 启动
    ```bash
    java -jar jenkins.war --httpPort=8080.
    ```
3. 个人选择安装了社区默认的插件
4. 设置账户密码: username/password
5. 设置 Jenkins URL: http://localhost:8080/

### Creating your first Pipeline

1. 使用 NodeJS 示例初始化 Git 仓库

    ```Jenkinsfile
    Jenkinsfile (Declarative Pipeline)
    pipeline {
        agent { docker { image 'node:6.3' } }
        stages {
            stage('build') {
                steps {
                    sh 'npm --version'
                }
            }
        }
    }
    ```

2. 选择多分支流水线
3. 添加资源

### Running multiple steps
