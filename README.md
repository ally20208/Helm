## 方法一：

設定多個 values file ，在 template 內設定單個 deployment 與 service ，透過指令部署多個 deployment。

![image](https://user-images.githubusercontent.com/110520606/226794286-3b8f315b-fae8-4374-8e0a-dbc8c2dde920.png)

執行指令時指定 values file 和名稱，則可以同目錄下執行多個服務

```console
helm install --values values.yaml ally .
```

```console
helm install --values values-1.yaml ally2 .
```

## 方法二：

設定一對一的 values yaml 和 deployment 及 service，此方式雖設定較多檔案，但可用一行指令執行部署。

不指定 values file

```console
helm install test .
```

指定 values file

```console
helm install test --values values.yaml,values-app3.yaml
```

創建一個 Helm Chart，例如 my-app。

在 my-app 目錄下，創建三個 values.yaml 文件，分別對應三個應用的配置選項，例如：

![image](https://user-images.githubusercontent.com/110520606/227875576-07d5907f-9805-4c3b-a096-1cad3c6b6106.png)

創建三個 deployment.yaml 模板文件，分別對應三個應用的 Deployment 配置。例如：

![image](https://user-images.githubusercontent.com/110520606/227875911-76686cf8-5a1c-4336-b7a6-80c50a8fa841.png)
