��**jQuery**��`att`r��`prop`�ᵽ����IE9֮ǰ�汾�����ʹ��`property`����������ڴ�й¶���⣬���ҹ���`Attribute`��`Property`������Ҳ����ʮ��ͷʹ����HTML5�������`data-*`�ķ�ʽ��**�Զ�������**����ν`data-*`ʵ�����Ͼ���`data-`ǰ׺�����Զ������������ʹ�������Ľṹ���Խ������ݴ�š�ʹ��`data-*`����**����Զ������Ի����޹������״**��

### 1. ��д��ʽ
`data-*`���������÷�ʽ������ֱ����`HTMLԪ�ر�ǩ`����д��
```html
<div id="test" data-age="24">
    Click Here
</div>
```
���е�`data-age`����һ���Զ������ԣ���Ȼ����Ҳ����ͨ��**JavaScript**��������в�����**HTML5**��Ԫ�ض�����һ��`dataset`�����ԣ�����һ��`DOMStringMap`���͵ļ�ֵ�Լ��ϣ�
```js
var test = document.getElementById('test');
test.dataset.my = 'Byron';
```
������Ϊ`div`�����һ��`data-my`���Զ������ԣ�ʹ��JavaScript����`dataset`��������Ҫע��ĵط���  

- 1. ������**���**��**��ȡ**���Ե�ʱ����Ҫȥ��ǰ׺`data-*`�����������������û��ʹ��`test.dataset.data-my = 'Byron';`����ʽ��

- 2. ������������л��������ַ�(`-`)����Ҫת��**�շ�����**��ʽ���������CSS��ʹ��ѡ������������Ҫʹ�����ַ���ʽ��

Ϊ�ղŴ���׷��д���ݣ� 
```html
<style type="text/css">
    [data-birth-date]{
        background-color: #0f0;
        width:100px;
        margin:20px;
    }
</style>
```

```js
test.dataset.birthDate = '19890615';
```
��������ͨ��JavaScript������data-birth-date�Զ������ԣ���CSS��ʽ��Ϊdiv�����һЩ��ʽ������Ч��

![ͼƬ1](http://p3nqtyvgo.bkt.clouddn.com/2018100601.png)

![ͼƬ2](http://p3nqtyvgo.bkt.clouddn.com/2018100602.png)

��ȡ��ʱ��Ҳ��ͨ��`dataset`����ʹ�á�`.`������ȡ���ԣ�ͬ����Ҫȥ��`data-`ǰ׺�����ַ���Ҫת��Ϊ�շ�����

```js
var test = document.getElementById('test');
test.dataset.my = 'Byron';
test.dataset.birthDate = '19890615';
test.onclick = function () {
    alert(this.dataset.my + ' ' + this.dataset.age+' '+this.dataset.birthDate);
}
```
![ͼƬ3](http://p3nqtyvgo.bkt.clouddn.com/2018100603.png)

### 2. getAttribute/setAttribute
��Щͬѧ���ܻ������`getAttribute`/`setAttribute`����������ʲô��������������һ�£�
```js
var test = document.getElementById('test');
test.dataset.birthDate = '19890615';
test.setAttribute('age', 25);
test.setAttribute('data-sex', 'male');

console.log(test.getAttribute('data-age')); //24
console.log(test.getAttribute('data-birth-date')); //19890516
console.log(test.dataset.age); //24
console.log(test.dataset.sex); //male
```

![ͼƬ4](http://p3nqtyvgo.bkt.clouddn.com/2018100604.png)

![ͼƬ5](http://p3nqtyvgo.bkt.clouddn.com/20181006045.png)


�������ǿ��Կ��������߶����������õ���`attribute��`���ϻ���Ҫ���˼��ܽ��Զ������ԣ���Ҳ����˵`getAttribute`/`setAttribute`���Բ������е�`dataset`���ݣ�`dataset`����ֻ��`attribute`��һ���Ӽ���������������������ˣ�����`dataset`��ֻ�д���`data-`ǰ׺�����ԣ�û��`age=25`�Ǹ�����

��ôΪʲô���ǻ�Ҫ��`data-*`�أ�һ�����ĺô������ǿ��԰������Զ���������`dataset`������ͳһ��������������Ķ�Ŷ�ܷ��㣬������������ɢɢ�ˣ��������û��ǲ���ġ�

### 3. �����������
�Ƚϲ��õ���Ϣ����`data-*`����������������ʮ�ֲ��ֹۡ�
* **Internet Explorer 11+**
* **Chrome 8+**
* **Firefox 6.0+**
* **Opera 11.10+**
* **Safari 6+**

����IE11+��ֱ������ϹС�����ۣ�����Ҫ��ȫ��ʹ�ô�����·��������Զ�ӡ�

