������Ҫ�ú��ܽ�һЩ֪ʶ������������������Ȼ�кö�֪ʶ������ᣬ���ǻ���ҪŬ��һ�£��������ֶ�����˭֪����~

## �������

h5֮ǰ���洢��Ҫ����`cookies`��`cookies`ȱ����**������ͷ�ϴ�������**����С��**4k֮��**����Domain��Ⱦ��

��ҪӦ�ã����ﳵ���ͻ���¼

����IE�������`UserData`����С��64k,ֻ��IE�����֧�֡�
 
## Ŀ��
���4k�Ĵ�С����  
�������ͷ�����洢��Ϣ������  
�����ϵ�ʹ洢������  
�������  
 
### 1.���ش洢localstorage
* **�洢��ʽ**��

��`��ֵ��`(`Key-Value`)�ķ�ʽ�洢��**���ô洢**��**����ʧЧ**��**�����ֶ�ɾ��**��
 
* **��С**��

ÿ������**5M**
 
* **֧�����**��
![ͼƬ1](http://p3nqtyvgo.bkt.clouddn.com/2018100701.png)

ע�⣺IE9 `localStorage`��֧�ֱ����ļ�����Ҫ����Ŀ�𵽷��������ſ���֧�֣�
 
* **��ⷽ��**��
```js
if(window.localStorage){
    alert('This browser supports localStorage');
}else{
    alert('This browser does NOT support localStorage');
}
``` 

* **���õ�API**��
```
getItem     //ȡ��¼

setIten     //���ü�¼

removeItem  //�Ƴ���¼

key         //ȡkey����Ӧ��ֵ

clear       //�����¼
```

![ͼƬ2](http://p3nqtyvgo.bkt.clouddn.com/2018100702.png)


* **�洢������**��

���飬ͼƬ��json����ʽ���ű���������ֻҪ�������л����ַ��������ݶ����Դ洢��

### 2.���ش洢sessionstorage
HTML5 �ı��ش洢 API �е� `localStorage` �� `sessionStorage` ��ʹ�÷���������ͬ�ģ��������� `sessionStorage` ��**�ر�ҳ��󼴱����**���� `localStorage` ���**һֱ����**��
 
### 3.���߻��棨application cache��
���ػ���Ӧ��������ļ�

* **ʹ�÷���**��

����**manifest�ļ�**

ҳ���ϣ�
```html
<!DOCTYPE HTML>
<html manifest="demo.appcache">
...
</html>
```

**Manifest �ļ�**��

manifest �ļ��Ǽ򵥵��ı��ļ�������֪���������������ݣ��Լ�����������ݣ���

manifest �ļ��ɷ�Ϊ�������֣�

1. **CACHE MANIFEST** - �ڴ˱������г����ļ������״����غ���л���

2. **NETWORK** - �ڴ˱������г����ļ���Ҫ������������ӣ��Ҳ��ᱻ����

3. **FALLBACK** - �ڴ˱������г����ļ��涨��ҳ���޷�����ʱ�Ļ���ҳ�棨���� 404 ҳ�棩

����demo��
```
CACHE MANIFEST
# 2016-07-24 v1.0.0
/theme.css
/main.js
 
NETWORK:
login.jsp
 
FALLBACK:
/html/ /offline.html
```

�������ϣ�manifest�ļ���Ҫ������ȷ��`MIME-type`���� "`text/cache-manifest`"��  

��Tomcat:
```html
<mime-mapping>
     <extension>manifest</extension>
     <mime-type>text/cache-manifest</mime-type>
</mime-mapping>
```

**����API**��

������`applicationCache����`���и�`status`���ԣ���ʾӦ�û���ĵ�ǰ״̬��

**0**��UNCACHED�� :  �޻��棬 ��û����ҳ����ص�Ӧ�û���

**1**��IDLE�� : ���ã���Ӧ�û���δ�õ�����

**2** ��CHECKING�� : ����У����������������ļ���������

**3** ��DOWNLOADING�� : �����У���Ӧ�û����������������ļ���ָ������Դ

**4** ��UPDATEREADY�� : ������ɣ�������Դ�����������

**5** ��IDLE�� :  ��������Ӧ�û���������ļ��Ѿ��������ˣ����ҳ���޷��ٷ���Ӧ�û���

 

**��ص��¼�**��

��ʾӦ�û���״̬�ĸı䣺

**checking** : �������ΪӦ�û�����Ҹ���ʱ����

**error** : �ڼ����»�������Դ�ڼ䷢�ʹ���ʱ����

**noupdate** : �ڼ�������ļ������ļ��ޱ仯ʱ����

**downloading** : �ڿ�ʼ����Ӧ�û�����Դʱ����

**progress**�����ļ�����Ӧ�û���Ĺ����г������ϵ����صش���

**updateready** : ��ҳ���µ�Ӧ�û���������ϴ���

**cached** : ��Ӧ�û�����������ʱ����

**Application Cache����������**��

1. �������
2. ����ҳ�������ٶ�

3. ���ͷ�����ѹ��

**ע������**��
1. ������Ի������ݵ��������ƿ��ܲ�̫һ����ĳЩ��������õ�������ÿ��վ�� 5MB����
2. ���manifest�ļ��������ڲ��оٵ�ĳһ���ļ������������أ��������¹��̽���Ϊʧ�ܣ����������ȫ��ʹ���ϵĻ��档
3. ����manifest��html������manifest�ļ�ͬԴ����ͬһ�����¡�
4. ��������Զ���������manifest�ļ���HTML�ļ�����͵����������HTML���ݣ�Ҳ��Ҫ���°汾�����������¡�
5. manifest�ļ���CACHE����NETWORK��FALLBACK��λ��˳��û�й�ϵ���������ʽ������Ҫ����ǰ�档
6. FALLBACK�е���Դ�����manifest�ļ�ͬԴ��
7. ������汾�󣬱���ˢ��һ�βŻ������°汾���������ˢһ��ҳ������������Ҫ��Ӽ����汾�¼���
8. վ���е�����ҳ�漴ʹû������manifest���ԣ��������Դ����ڻ�����Ҳ�ӻ����з��ʡ�
9. ��manifest�ļ������ı�ʱ����Դ������Ҳ�ᴥ�����¡�


**���߻����봫ͳ�������������**��

1. ���߻������������Ӧ�ã�����������ǵ����ļ�

2. ���߻�������˻��ǿ��Դ�ҳ�棬��������治��

3. ���߻����������֪ͨ�����������Դ

### 4.Web SQL
**��ϵ���ݿ�**��ͨ��SQL������

Web SQL ���ݿ� API ������ HTML5 �淶��һ���֣���������һ�������Ĺ淶��������һ��ʹ�� SQL �����ͻ������ݿ�� APIs��
 
**֧�����**��
Web SQL ���ݿ���������°�� **Safari**, **Chrome** �� **Opera** ������й�����
 
**���ķ���**��

1. **openDatabase**���������ʹ�����е����ݿ�����½������ݿⴴ��һ�����ݿ����

2. **transaction**����������������ܹ�����һ�������Լ������������ִ���ύ���߻ع���

3. **executeSql**�������������ִ��ʵ�ʵ� SQL ��ѯ��

 

**�����ݿ�**��
```js
var db = openDatabase('mydb', '1.0', 'Test DB', 2 * 1024 * 1024,fn);
//openDatabase() ������Ӧ����������ֱ�Ϊ�����ݿ����ơ��汾�š������ı������ݿ��С�������ص�
```

**ִ�в�ѯ����**��
```js
var db = openDatabase('mydb', '1.0', 'Test DB', 2 * 1024 * 1024);
db.transaction(function (tx) { 
   tx.executeSql('CREATE TABLE IF NOT EXISTS WIN (id unique, name)');
});
```

**��������**����
```js
var db = openDatabase('mydb', '1.0', 'Test DB', 2 * 1024 * 1024);
db.transaction(function (tx) {
   tx.executeSql('CREATE TABLE IF NOT EXISTS WIN (id unique, name)');
   tx.executeSql('INSERT INTO WIN (id, name) VALUES (1, "winty")');
   tx.executeSql('INSERT INTO WIN (id, name) VALUES (2, "LuckyWinty")');
});
```

**��ȡ����**��
```js
db.transaction(function (tx) {
   tx.executeSql('SELECT * FROM WIN', [], function (tx, results) {
      var len = results.rows.length, i;
      msg = "<p>��ѯ��¼����: " + len + "</p>";
      document.querySelector('#status').innerHTML +=  msg;
     
      for (i = 0; i < len; i++){
         alert(results.rows.item(i).name );
      }
     
   }, null);
});
```
����Щ�������Կ����������϶�����SQL���������ݿ����ز�����������MySQL�Ļ������Ӧ�ñȽ������á�


### 5.IndexedDB
�������ݿ� (IndexedDB) API����Ϊ HTML5 ��һ���֣��Դ������зḻ���ش洢���ݵ������ܼ��͵����� HTML5 Web Ӧ�ó�������á�ͬʱ����������**���ػ�������**��ʹ��ͳ���� Web Ӧ�ó��򣨱����ƶ� Web Ӧ�ó����ܹ�**��������к���Ӧ**��
 
**�첽API**��
��IndexedDB�󲿷ֲ������������ǳ��õĵ��÷��������ؽ����ģʽ���������󡪡���Ӧ��ģʽ����������ݿ�Ĳ���

![ͼƬ3](http://p3nqtyvgo.bkt.clouddn.com/2018100703.png)

���������Ǵ����ݿ��ʱ��ʵ���Ϸ�����һ��DB���󣬶�����������`result`�С�����ͼ���Կ���������result֮�⡣���м�����Ҫ�����Ծ���`onerror`��`onsuccess`��`onupgradeneeded`����������򿪵����ݿ�İ汾�ź��Ѿ����ڵ����ݿ�汾�Ų�һ�µ�ʱ����ã���������������ǵ�ajax�������������Ƿ������������֮�󲢲���ȷ����ʲôʱ�������ɹ���������Ҫ�ڻص��д���һЩ�߼���
 
**�ر���ɾ��**��
```js
function closeDB(db){
     db.close();
}
function deleteDB(name){
     indexedDB.deleteDatabase(name);
}
```

**���ݴ洢**��

**indexedDB**��û�б�ĸ������`objectStore`��һ�����ݿ��п��԰������`objectStore`��`objectStore`��һ���������ݽṹ�����Դ�Ŷ����������ݡ�Ҳ����˵һ��`objectStore`�൱��һ�ű�����洢��ÿ�����ݺ�һ�����������

���ǿ���ʹ��ÿ����¼�е�ĳ��ָ���ֶ���Ϊ**��ֵ**��keyPath����Ҳ����ʹ���Զ����ɵĵ���������Ϊ��ֵ��keyGenerator����Ҳ���Բ�ָ����ѡ��������Ͳ�ͬ��objectStore���Դ洢�����ݽṹҲ�в��졣��

������е㸴���ˡ�������Ľ̳̣�
1.http://www.cnblogs.com/dolphinX/p/3415761.html��

2.http://www.cnblogs.com/dolphinX/p/3416889.html
��ϸAPI��ַ��http://www.ibm.com/developerworks/cn/web/wa-indexeddb/#ibm-pcon
 
��ʱ��������ȷʵ��Щ�洢��ʽδ�����ù���Ҳֻ����Щ���˵������ˡ����˽����ţ��Ժ��õ�����ϸ��¼�ɣ�^_^