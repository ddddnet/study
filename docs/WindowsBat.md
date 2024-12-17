# Windows 批处理指令

`cmd /k` 展示命令行窗口

实例:一键push到git

```jsx
@echo off
cd D:\apache-jmeter-4.0\bin\wms_performance   #wms_performance为本地git仓库目录
git add .   #直接执行git命令
git commit -m 'perfromanceTest'
git push -u origin master
```