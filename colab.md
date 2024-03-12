## 防掉线

避免断开连接的方法是，通过console的JavaScript来完成，在网页内，按键 Ctrl Shift + I， 跳到cosole的tab，输入以下的内容：

Chrome 复制前需要手动输入 allow pasting
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
