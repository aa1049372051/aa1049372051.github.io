复制正常格式图片的方法（这里使用getSelection+execCommand api的方法）：
```javascript
// 创建一个图片元素
let imgEle = document.createElement("img");
// 找到想要复制的图片元素
let picture = document.getElementById('img-picture');
// 将图片属性复制到新创建的图片元素上
imgEle.src = picture.src;
imgEle.id = `img-${picture.id}`;

document.body.appendChild(imgEle);
let selection = window.getSelection();
let range = document.createRange();
range.selectNode(document.getElementById(imgEle.id));
selection.removeAllRanges();
selection.addRange(range);
document.execCommand("copy");
document.body.removeChild(imgEle);


针对base-64格式图片，需要先将base-64解码，转为blob格式，再用navigator.clipboard方法
具体如下：
```javascript
const blobInput = this.base64ToBlob(imgEle.src, 'image/png');
const clipboardItemInput = new ClipboardItem({ 'image/png': blobInput });
navigator.clipboard.write([clipboardItemInput]);

base64ToBlob(base64Data, contentType) {
    // base64 解码
    let byteString = window.atob(base64Data.substring(base64Data.indexOf(',') + 1));
    // 创建缓冲数组
    let arrayBuffer = new ArrayBuffer(byteString.length);
    // 创建视图
    let intArray  = new Uint8Array(arrayBuffer);
    for (let i = 0; i < byteString.length; i++) {
        intArray[i] = byteString.charCodeAt(i);
    }
    return new Blob([intArray], { type: contentType });
}