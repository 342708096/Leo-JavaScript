> [ԭ�ĵ�ַ](https://segmentfault.com/a/1190000016678888)

## this
* ES6�е�**��ͷ����**���õ���**�ʷ�������**��
* ΪʲôҪʹ��this��**ʹAPI��Ƶø���������ڸ���**��
* this����ָ������Ҳ��ָ�����Ĵʷ�������
* this��ָ��ֻȡ����**�����ĵ��÷�ʽ**��

## this�󶨹���
* new > ��ʾ�� > ��ʽ�� > Ĭ�ϰ�

### Ĭ�ϰ�

* ��������������ʱ�������Ƿ��ڵ���ջ�У�this��ָ��**ȫ�ֶ���**���������Ϊwindow��
* �ϸ�ģʽ�£����ܽ�ȫ�ֶ�������Ĭ�ϰ󶨡�
```js
var a = 2;
function foo(){
    console.log(this.a);
}
function bar(){
    var a = 5;
    foo();
}
bar(); // 2
```

### ��ʽ��

* �����������������Ķ���ʱ����ʽ�󶨹����Ѻ��������е�`this`�󶨵���������Ķ���
* ����������������ֻ�����һ���ڵ���λ���������á�
* Ҫ�󣺶����ڲ��������һ��ָ���������ԣ��ö����ͨ��������Լ�����ú�����
```js
function foo() {
    console.log( this.a );
}

var obj2 = {
    a: 42,
    foo: foo
};

var obj1 = {
    a: 2,
    obj2: obj2
};

obj1.obj2.foo(); // 42
```

* ��ʽ��ʧ
```js
function foo() {
    console.log( this.a );
}

var obj = {
    a: 2,
    foo: foo
};

var bar = obj.foo; // ����bar������foo�����������Բ����к��������������

var a = "oops, global"; // a��ȫ�ֶ��������

bar(); // "oops, global"
```

�ͻص�����������£���������ʱ����ʽ��ֵ��

```js
function foo() {
    console.log( this.a );
}

function doFoo(fn) {
    // ��������ʱ���൱��fn = obj.foo���ͺ��ϸ�����һ����
    fn(); // <-- call-site!
}

var obj = {
    a: 2,
    foo: foo
};

var a = "oops, global"; // `a` also property on global object

doFoo( obj.foo ); // "oops, global"
```

### ��ʽ��

* ����`call()`��`apply()`��ͨ������һ��������Ϊ�������ͣ��ᱻ��װ����תΪ����װ�䣩����`this`�󶨵��ö���
* Ӳ��

```js
function foo() {
    console.log( this.a );
}

var obj = {
    a: 2
};

var bar = function() {
    foo.call( obj );
};

bar(); // 2
setTimeout( bar, 100 ); // 2

// Ӳ�󶨺�bar������ô���ã�������Ӱ��foo������this��
bar.call( window ); // 2
```

Ӳ�󶨵ĵ���Ӧ�������µİ���������

```js
function foo(something) {
    console.log( this.a, something );
    return this.a + something;
}

var obj = {
    a: 2
};

var bar = function() {
    return foo.apply( obj, arguments ); // ��obj����Ӳ�����ȥ
};

var b = bar( 3 ); // 2 3
console.log( b ); // 5
```

�����ڲ�������`apply`Ӳ�󶨵�ĳ������������ô�����������������������Ӱ���ڲ�������`this`��
`bind`�����������£�

```js
function foo(something) {
    console.log( this.a, something );
    return this.a + something;
}

// simple `bind` helper
function bind(fn, obj) {
    return function() {
        return fn.apply( obj, arguments ); // ���ò�����obj�����ȥ
    };
}

var obj = {
    a: 2
};

var bar = bind( foo, obj ); // bind( foo, obj )�᷵��һ����������

var b = bar( 3 ); // 2 3
console.log( b ); // 5
```
* **�ܽ�**������������������Ҫ��������������ֻ��һ��һ���ظ�д��Ӳ����ķ�ʽ���²��ܱ����ã���ĳ�ֹ�����Ҫ����ظ�ʹ��ʱ����������������Ϊ������

## new��
�κκ��������ܱ��������캯������������`new`��������**�������**��ʱ����ִ�����������
 1. ����һ���¶������ú�������JS���õģ��򴴽�һ���µ�Object���󣩣�
 2. ��this�󶨵��������
 3. ִ�й��캯���еĴ��루Ϊ����¶���������ԣ���
 4. ������û�з��������������Զ���������¶�����������return���ص��ǷǶ��������Զ���������¶��󣬼������Ǹ��Ƕ���

```js
function foo(a) {
    this.a = a;
}

var bar = new foo( 2 );
console.log( bar.a ); // 2
```

### ����˵��
* �������
```js
function foo() {
    console.log( this.a );
}

var a = 2;
var o = { a: 3, foo: foo };
var p = { a: 4 };

o.foo(); // 3
(p.foo = o.foo)(); // 2������p.foo = o.foo�ķ���ֵ��Ŀ�꺯�������ã����Ե���λ����foo()��������p.foo()��o.foo()
```

* **��ͷ����**����ʹ�����ĸ�this���򣬸���**�ʷ�������**������`this`��
```js
function foo() {
    // ����һ����ͷ����
    return (a) => {
        // `this` here is lexically adopted from `foo()`
        console.log( this.a );
    };
}

var obj1 = {
    a: 2
};

var obj2 = {
    a: 3
};

// foo()���Ǽ�ͷ����������this���󶨵�obj1
var bar = foo.call( obj1 ); // foo.call( obj1 )���ؼ�ͷ����������barΪ��ͷ����
bar.call( obj2 ); // 2! ��ͷ������this�޷����޸ģ�newҲ����
```

����Ϊ�ͼ�ͷ����һ����ģʽ��

```js
function foo() {
    var self = this; // lexical capture of `this`
    setTimeout( function(){
        console.log( self.a );
    }, 100 );
}

var obj = {
    a: 2
};

foo.call( obj ); // 2
```

this�󶨵�Ȥ�⣺
[֪������-arguments�������](https://www.zhihu.com/question/21466212)