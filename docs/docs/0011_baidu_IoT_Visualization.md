# baidu IoT Hub IoT Visualization sign-aas

## 参考文档

* [部署](https://cloud.baidu.com/doc/IOTVIZ/GettingStarted.html#.E5.90.8E.E7.AB.AF.E9.9B.86.E6.88.90)
* [集成到 React 应用中](https://cloud.baidu.com/doc/IOTVIZ/BestPractise.html#.E4.BF.AE.E6.94.B9.E4.BB.A3.E7.A0.81)

## Token Tool Download

* [sign-aas](http://iot-dv.cdn.bcebos.com/v2/sdk/sign-aas.jar)

## sign-aas help

```
C:\Users\aplex\Desktop\mqtt\docs\refers>java -jar sign-aas.jar
2017-12-13 09:16:46.781:INFO::main: Logging initialized @7282ms
使用方法：java -jar 文件名.jar [options] [配置文件.json]

options 选项列表：
      --ak AccessKey        指定AccessKey，结合默认配置使用
      --sk SecretAccessKey  指定SecretAccessKey，结合默认配置使用
  -p, --port PORT           监听的端口号，默认8080
  -h, --host HOST           监听的机器名/IP地址，默认为localhost
  -s, --sync                指定服务以同步方式运行，默认为false
      --max-threads NUM     最大线程数量，同步(sync)方式时无效，默认为50
      --min-threads NUM     最小线程数量，同步(sync)方式时无效，默认为8

基本使用方法:
java -jar sign-aas.jar --ak 你的AK --sk 你的SK服务会根据默认配置提供 /tokens endpoint，用以获取物可视的访问token。

高级使用方法:
java -jar sign-aas.jar [options] 配置文件.json
自定义配置内容为一个JSON数组，数组元素为JSON对象，格式如下：
{
    "path": "本地路径通配符, 例如 /tokens**",
    "target": {
        "url": "目标服务地址，例如 https://viz.baidubce.com/",
        "path": "目标服务的路径，替换本地路径通配符中的具体路径，例如 /v2/tokens
"
    },
    "ak": "你的 AccessKey",
    "sk": "你 的SecretAccessKey"
}
如上配置会将发至 /tokens 路径下的请求加上Ak+Sk签名，转发至 https://viz.baidubce.com/v2/tokens。
```

## 运行sign-ass

```
C:\Users\aplex\Desktop\mqtt\docs\refers>java -jar sign-aas.jar --ak=5c5b5ea289ed4c6db75c131e7eaf5715 --sk=ca49ed4d426541e79f7da83fde4b9e28
2017-12-13 09:46:41.731:INFO::main: Logging initialized @1155ms
2017-12-13 09:46:43.597:INFO:oejs.Server:main: jetty-9.2.z-SNAPSHOT
2017-12-13 09:46:44.063:INFO:oejs.ServerConnector:main: Started ServerConnector@
1bd13f0c{HTTP/1.1}{localhost:8080}
2017-12-13 09:46:44.065:INFO:oejs.Server:main: Started @3490ms
```

## 处理方式

* [../code/IoT_Visualization/sign-ass.py](../code/IoT_Visualization/sign-ass.py)
* [../code/IoT_Visualization/bce_tokens.py](../code/IoT_Visualization/bce_tokens.py)

## IoT Visualization

![../img/Biadu_IoT_Hub_IoT_VZ_UI.png](../img/Biadu_IoT_Hub_IoT_VZ_UI.png)
