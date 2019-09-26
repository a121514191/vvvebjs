# vvvebjs

# 介紹

VvvebJs是一個開源的網頁拖拽自動生成的JavaScript庫

你可以以簡單拖拽的方式生成自己需要的網頁樣式，內置jquery和Bootstrap

可以拖拽相關的組件進行網頁的構建

![](https://github.com/a121514191/vvvebjs/blob/master/home.PNG)


# 實作

github網址

https://github.com/givanz/VvvebJs

直接 clone 或是 下載zip檔

下載完後有 VvvebJs-master 資料夾檔案

可以直接開啟裡面的 editor.html 

頁面可以開啟但是功能不完全(無法存檔，可下載但url錯誤，無法新增屬於自己的版型)

# 問題處理

將檔案放進xampp的htdocs

放入後開啟 editor.html

檔案至少可以存檔(但new page的按鈕還是無法執行，且有一個版型無法開啟)


![](https://github.com/a121514191/vvvebjs/blob/master/error.PNG)

![](https://github.com/a121514191/vvvebjs/blob/master/error2.PNG)

## Step2.下載為Google Cloud SDK的一部分

參考網址: https://cloud.google.com/sdk/docs/quickstart-redhat-centos

如果您還沒有 Google Cloud Platform 專案，請建立 Google Cloud Platform 專案

建立後如圖

![](https://github.com/a121514191/docker_Kubernetes/blob/master/google%20cloud.PNG)

# centos 安裝 Cloud SDK 

*Update YUM with Cloud SDK repo information: 

```
sudo tee -a /etc/yum.repos.d/google-cloud-sdk.repo << EOM
[google-cloud-sdk]
name=Google Cloud SDK
baseurl=https://packages.cloud.google.com/yum/repos/cloud-sdk-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg
       https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOM
```

*The indentation for the 2nd line of gpgkey is important.
*Install the Cloud SDK

```
sudo yum install google-cloud-sdk
```
# 完成後 初始化 SDK

```
gcloud init
```

# 初始化完成後會要求你登入 使用 Google 使用者帳戶並接受登入選項：

To continue, you must log in. Would you like to log in (Y/n)? Y

![](https://github.com/a121514191/docker_Kubernetes/blob/master/google-login.PNG)

擷取字串貼至瀏覽器，會要求你登入google，登入完成後會給你驗證碼

![](https://github.com/a121514191/docker_Kubernetes/blob/master/password.PNG)

成功進入後 可以看到你在 google cloud platform 所建立的專案

![](https://github.com/a121514191/docker_Kubernetes/blob/master/project.PNG)

選取你有的專案或是新增一個，成功執行後如下圖(我選擇已建立好的)

![](https://github.com/a121514191/docker_Kubernetes/blob/master/cloud%20finish.PNG)

# 執行核心 gcloud 指令

列出本機系統上已儲存憑證的帳戶

```
gcloud auth list
```

![](https://github.com/a121514191/docker_Kubernetes/blob/master/list.PNG)

列出您所使用 SDK 配置中的屬性：

```
gcloud config list
```

![](https://github.com/a121514191/docker_Kubernetes/blob/master/config.PNG)

其餘指令可參考網址: https://cloud.google.com/sdk/docs/quickstart-redhat-centos

# gcloud運行kubectl安裝命令

```
gcloud components install kubectl
```

出錯

![](https://github.com/a121514191/docker_Kubernetes/blob/master/error.PNG)

您無法執行此操作，因為Cloud SDK組件管理器，已禁用此安裝

## Step3. 跳過錯誤，先驗證kubectl配置

通過獲取群集狀態檢查kubectl是否已正確配置：

```
kubectl cluster-info
```

如果您看到URL響應，則kubectl已正確配置為訪問您的群集。

如果您看到類似於以下內容的消息，則kubectl配置不正確或無法連接到Kubernetes群集。

```
The connection to the server <server-name:port> was refused - did you specify the right host or port?
```

![](https://github.com/a121514191/docker_Kubernetes/blob/master/error2.PNG)

如果是使用Minikube 可用以下語法檢查配置

```
kubectl cluster-info dump
```

## Step4. kubectl配置

啟用shell自動完成功能

```
kubectl completion bash
```

完成腳本依賴於bash-completion

可以測試是否已通過運行安裝了bash-completion -> type _init_completion

安裝bash-completion

```
apt-get install bash-completion

yum install bash-completion
```

上面的命令創建/usr/share/bash-completion/bash_completion
重新加載shell並通過鍵入驗證是否正確安裝了bash-completion

```
source /usr/share/bash-completion/bash_completion

type _init_completion
```

參考網址:
*google-cloud
1. https://cloud.google.com/sdk/docs/quickstart-redhat-centos
*kubernetes
2. https://kubernetes.io/docs/tasks/tools/install-kubectl/










