## 防掉线
```
function ConnectButton(){
    console.log("Connect pushed"); 
    document.querySelector("#top-toolbar > colab-connect-button").shadowRoot.querySelector("#connect").click() 
}
setInterval(ConnectButton,60000);
```
```
function ConnectButton(){
    
};
```

## 挂载
```
from google.colab import drive
drive.mount('/content/drive')
%cd /content/drive/MyDrive/
```
