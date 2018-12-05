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

可以对步骤( step )进行定义，执行次数，超时时间等等..

### Defining execution environments

直接使用 Docker 就很好，使用 `agent` 属性设置

### Using environment variables

设置环境变量，使用 `environment` 属性设置

### Recording tests and artifacts

基于 post/always 下的 `archiveArtifacts` 以及 `junit`  

### Cleaning up and notifications

在 post 目录下使用 `deleteDir()` 以及发起邮件通知，支持 Email、Slack 等方式

### deploy

其实就是在一个特定的 stage 执行相应的脚本啦！