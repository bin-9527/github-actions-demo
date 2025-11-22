自动部署案例

一个工作流，就是一个yaml文件，就是一个可以执行具体命令的容器
工作流之间默认的工作方式是并发。
作业有哪些配置？
配置	说明	是否必输
jobs.job_id	作业的id	是
jobs.job_id.runs-on	定义运行job时的计算机类型。其实就相当于指定服务器的运行系统。	是
jobs.job_id.steps	完成id为job_id的任务，需要执行的步骤集合。	是
jobs.job_id.steps.run	执行shell命令，相当于node里的child_process。	是
jobs.job_id.steps.use	用于获取你上传的代码。	是
jobs.job_id.name	当前作业id的名称。如果你只配置里job_id，那么平台会认为作业的id、name是一样的。	否
jobs.job_id.needs	定义job之间的关系	否

name: CI
on:
  push:
    branches: [ main ]//指定分支

