#使用javascript解析获取ActiveX控件


1. 使用chrome打开含有ActiveX的页面

2. Ctrl+Shift+I 进入开发工具

3. 进入javascript控制台

4. 统计静态ActiveX控件的数量:
```
alert(document.getElementsByTagName("object").length)
```
5. 取得ActiveX控件
```
alert(document.getElementsByTagName("object")[0].outerHTML)
//firefox不支持outerHTML
```
6. 待解决: 通过ActiveX动态插入的ActiveX控件如何取得?


取得控件并且对HTML进行格式化
```
var AttrList=new Array(' id="',' name="',' classid="',' codebase="',' width="',' style="');
ObjectCount=document.getElementsByTagName("object").length;
for (i=0;i<ObjectCount;i++){
    ObjectElement=document.getElementsByTagName("object")[i];
    ObjectElement.innerHTML="";
    ObjectHTML=ObjectElement.outerHTML;
    ObjectHTMLformatted=ObjectHTML;
    for (j=0;j<AttrList.length;j++){
        ObjectHTMLformatted=ObjectHTMLformatted.replace(AttrList[j],"\n\t"+AttrList[j]);
    }

    ObjectHTMLformatted=ObjectHTMLformatted.replace("</object>","\n</object>");

    alert(ObjectHTMLformatted);
}
```