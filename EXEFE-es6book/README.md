**�������**��  
- [x] ����  
- [x] Ŀ¼  
- [ ] ES6  
- [ ] ES7  
- [ ] ES8  
- [ ] ES9  
- [ ] ֪ʶ����  
> ������ 2018.10.18  
> Ҳ��˼��������������һ�����ϣ��ÿ����ˣ��������ջ�  

# һ������
������������Ѿ��и�ʽ�������� **ECMAScript** �淶�Ľ��ܺͷ��������£�����׼������һ�ݱȽ�����Ҳ�ȽϾ�����ڿ������ŵ����ϡ�  
������ϵ�**ES6����**����ο���һ����ʦ�� [ECMAScript6����](http://es6.ruanyifeng.com/) ����������������ʵ�õ����ݡ�  
����**ES7/ES8/ES9**��������ο�������  

# ����Ŀ¼
<!-- TOC -->

- [һ������](#һ����)
- [����Ŀ¼](#��Ŀ¼)
- [��������](#������)
    - [1. ES6](#1-es6)
        - [let �� const����](#let-��-const����)
            - [let ����](#let-����)
            - [const ����](#const-����)
        - [�����Ľ⹹��ֵ](#�����Ľ⹹��ֵ)
            - [1.����](#1����)
            - [2.����Ľ⹹��ֵ](#2����Ľ⹹��ֵ)
            - [3.�ַ����Ľ⹹��ֵ](#3�ַ����Ľ⹹��ֵ)
            - [4.��ֵ�Ͳ���ֵ�Ľ⹹��ֵ](#4��ֵ�Ͳ���ֵ�Ľ⹹��ֵ)
            - [5.���������Ľ⹹��ֵ](#5���������Ľ⹹��ֵ)
            - [6.��;](#6��;)
        - [�ַ�������չ](#�ַ�������չ)
            - [1.includes(),startsWith(),endsWith()](#1includesstartswithendswith)
            - [2.repeat()](#2repeat)
            - [3.padStart(),padEnd()](#3padstartpadend)
            - [4.ģ���ַ���](#4ģ���ַ���)
        - [�������չ](#�������չ)
        - [��ֵ����չ](#��ֵ����չ)
            - [1.Number.isFinite(), Number.isNaN()](#1numberisfinite-numberisnan)
            - [2.Number.parseInt(), Number.parseFloat()](#2numberparseint-numberparsefloat)
            - [3.Number.isInteger()](#3numberisinteger)
            - [4.Math�������չ](#4math�������չ)
            - [5.ָ�������](#5ָ�������)
        - [��������չ](#��������չ)
        - [�������չ](#�������չ)
    - [2. ES7](#2-es7)
    - [3. ES8](#3-es8)
    - [4. ES9](#4-es9)
    - [5. ֪ʶ����](#5-֪ʶ����)
        - [�鼶������](#�鼶������)
- [�ġ�����](#�Ľ���)

<!-- /TOC -->

# ��������
## 1. ES6

### let �� const����

��ES6�У�����ͨ��ʵ�� `let` ��ʾ**����**��`const` ��ʾ**����**������ `let` �� `const` ����**�鼶������**������**��ǰ��������Ч**�����ظ�������

#### let ����
`let` ������÷��� `var` ���ƣ����� `let` ֻ�����ڴ��������Ч��  
**�����÷�**��   
```js
{
    let a = 1;
    let b = 2;
}
```

���� `let` �������ص㣺  

* **�����ڱ���������**  
��ES6֮ǰ������ `var` ����һ��**����**һ��**����**����������ű������������⣬����ʵ�ʿ������̾�������һЩ�߼��ϵ��ɻ󣬰���һ��˼άϰ�ߣ�����������Ҫ��������ʹ�á�
```js
// var 
console.log(v1); // undefined
var v1 = 2;
// ���ڱ������� ����ʵ������
var v1;
console.log(v1)
v1 = 2;

// let 
console.log(v2); // ReferenceError
let v2 = 2;
```

* **�������ظ�������**  
`let` �� `const` ����ͬ�������£���**�����ظ�����ͬһ����**������**�����ں�����������������**��
```js
// 1. �����ظ�����ͬһ����
// ����
function f1 (){
    let a = 1;
    var a = 2;
}
// ����
function f2 (){
    let a = 1;
    let a = 2;
}

// 2. �����ں�����������������
// ����
function f3 (a1){
    let a1; 
}
// ������
function f4 (a2){
    {
        let a2
    }
}
```

#### const ����
`const` ����һ��**ֻ��**��**����**��  
**�����÷�**��  
```js
const PI = 3.1415926;
console.log(PI);  // 3.1415926

```
**ע���**��    
* `const` �������޷��޸�ֵ��  
```js
const PI = 3.1415926;
PI = 3; 
// TypeError: Assignment to constant variable.
```
* `const` ����ʱ�����븳ֵ��  
```js
const a ; 
// SyntaxError: Missing initializer in const declaration.
```
* `const` �����ĳ�����`let` �����ظ�������  
```js
const PI = 3.1415926;
let PI = 0;  
// Uncaught SyntaxError: Identifier 'PI' has already been declared
```


### �����Ľ⹹��ֵ
**�⹹��ֵ����**����ES6�У�ֱ�Ӵ�����Ͷ�����ȡֵ�����ն�Ӧλ�ã���ֵ�������Ĳ�����  

#### 1.����  
**�����÷�**��    
```js
// ES6 ֮ǰ
let a = 1;
let b = 2;

// ES6 ֮��
let [a, b] = [1, 2];
```

�����ϣ�ֻҪ�Ⱥ�����ģʽһ�£���߱������ɻ�ȡ�ұ߶�Ӧλ�õ�ֵ�������÷���  

```js
let [a, [[b], c]] = [1, [[2], 3]];
console.log(a, b, c); // 1, 2, 3

let [ , , c] = [1, 2, 3];
console.log(c);       // 3

let [a, , c] = [1, 2, 3];
console.log(a,c);     // 1, 3

let [a, ...b] = [1, 2, 3];
console.log(a,b);     // 1, [2,3]

let [a, b, ..c.] = [1];
console.log(a, b, c); // 1, undefined, []
```

**ע���**��    
* ����⹹���ɹ���������ֵ�͵���`undefined`��    
```js
let [a] = [];     // a => undefined
let [a, b] = [1]; // a => 1 , b => undefined
```
* �����ģʽ�����ұߣ�Ҳ���Խ⹹�ɹ���  
```js
let [a, b] = [1, 2, 3];
console.log(a, b); // 1, 2
```
* ����ģʽ��ͬ������  
```js
let [a] = 1;
let [a] = false;
let [a] = NaN;
let [a] = undefined;
let [a] = null;
let [a] = {};
```

**ָ���⹹��Ĭ��ֵ**��  
**�����÷�**��  
```js
let [a = 1] = [];      // a => 1
let [a, b = 2] = [a];  // a => 1 , b => 2
```
���������  
```js
let [a = 1] = [undefined]; // a => 1
let [a = 1] = [null];      // a => null
```
�ұ�ģʽ��Ӧ��ֵ�������ϸ����`undefined`��Ĭ��ֵ������Ч����`null`���ϸ����`undefined`��  

#### 2.����Ľ⹹��ֵ
������⹹��ͬ���ǣ�����⹹**����Ҫ�ϸ���˳��ȡֵ**����ֻҪ����**������**ȥȡ��Ӧ**������**��ֵ����ȡ������Ӧ**������**��ֵ����Ϊ`undefined` ��  

**�����÷�**��    
```js
let {a, b} = {a:1, b:2};  // a => 1 , b => 2
let {a, b} = {a:2, b:1};  // a => 2 , b => 1
let {a} = {a:3, b:2, c:1};// a => 3
let {a} = {b:2, c:1};     // a => undefined
```

**ע���**��  
* ��**������**��**������**��һ�£�����Ҫ�޸����ơ�
```js
let {a:b} = {a:1, c:2}; 
// error: a is not defined
// b => 1
```
����Ľ⹹��ֵ���ڲ����ƣ������ҵ�ͬ�����ԣ�Ȼ���ٸ�����Ӧ�ı�������������ֵ���Ǻ��ߣ�������ǰ�ߡ�  
��������У�`a` ��ƥ���ģʽ��`b`���Ǳ�������������ֵ���Ǳ���`b`��������ģʽ`a`��  

* ����⹹Ҳ֧��**Ƕ�׽⹹**�� 
```js
let obj = {
    a:[ 1, { b: 2}]
};
let {a, a: [c, {b}]} = obj;
// a=>[1, {b: 2}], b => 2, c => 1
```

**ָ���⹹��Ĭ��ֵ**�� 
```js
let {a=1} = {};        // a => 1
let {a, b=1} = {a:2};  // a => 2, b => 1

let {a:b=3} = {};      // b => 3
let {a:b=3} = {a:4};   // b = >4
// a��ģʽ��b�Ǳ��� �μ�

let {a=1} = {a:undefined};  // a => 1
let {a=1} = {a:null};   // a => null
// ��Ϊnull��undefined���ϸ���ȣ����Ը�ֵ��Ч
// ����Ĭ��ֵ1������Ч��
```

#### 3.�ַ����Ľ⹹��ֵ
�ַ����Ľ⹹��ֵ�У��ַ�����ת������һ��**��������Ķ���**�� 
**�����÷�**�� 
```js
const [a, b, c, d, e] = 'hello';
a // "h"
b // "e"
c // "l"
d // "l"
e // "o"

let {length:len} = 'hello';// len => 5
```

#### 4.��ֵ�Ͳ���ֵ�Ľ⹹��ֵ
�⹹��ֵ�Ĺ����ǣ�**ֻҪ�Ⱥ��ұߵ�ֵ���Ƕ�������飬���Ƚ���תΪ����**������`undefined`��`null`**�޷�תΪ����**�����Զ����ǽ��н⹹��ֵ�����ᱨ�� 
```js
// ��ֵ�Ͳ���ֵ�İ�װ������toString����
let {toString: s} = 123;
s === Number.prototype.toString // true
let {toString: s} = true;
s === Boolean.prototype.toString // true

let { prop: x } = undefined; // TypeError
let { prop: y } = null;      // TypeError
```

#### 5.���������Ľ⹹��ֵ
**�����÷�**��  
```js
function fun ([a, b]){
    return a + b;
}
fun ([1, 2]); // 3
```
**ָ��Ĭ��ֵ�Ľ⹹**: 
```js
function fun ({a=0, b=0} = {}){
    return [a, b];
}
fun ({a:1, b:2}); // [1, 2]
fun ({a:1});      // [1, 0]
fun ({});         // [0, 0]
fun ();           // [0, 0]

function fun ({a, b} = {a:0, b:0}){
    return [a, b];
}
fun ({a:1, b:2}); // [1, 2]
fun ({a:1});      // [1, undefined]
fun ({});         // [undefined, undefined]
fun ();           // [0, 0]
```

#### 6.��;
* **����������ֵ**: 
```js
let a = 1,b = 2;
[a, b] = [b, a]; // a =>2 , b => 1 
```

* **�������ض��ֵ**: 
```js
// ����һ������
function f (){
    return [1, 2, 3];
}
let [a, b, c] = f(); // a=>1, b=>2, c=>3

// ����һ������
function f (){
    return {a:1, b:2};
}
let {a, b} = f();    // a=>1, b=>2
```

* **���ٶ�Ӧ����**: 
���ٵĽ�һ��������������Ӧ�� 
```js
function f([a, b, c]) {...}
f([1, 2, 3]);

function f({a, b, c}) {...}
f({b:2, c:3, a:1});
```

* **��ȡJSON����**�� 
```js
let json = {
    name : 'leo',
    age: 18
}
let {name, age} = json;
console.log(name,age); // leo, 18
```

* **����Map�ṹ**: 
```js
const m = new Map();
m.set('a':1);
m.set('b':2);
for ([k, v] of m){
    console.log(k + ' : ' + v);
}
// ��ȡ����
for (let [k] of m){...}
// ��ȡ��ֵ
for (let [,k] of m){...}
```

* **����ģ���ָ������**: 
����**�������**ģ������Ҫ�õ��ķ����� 
```js
const {log, sin, cos} = require('math');

```

### �ַ�������չ
#### 1.includes(),startsWith(),endsWith()
�������ж��ַ����Ƿ������һ���ַ���ʱ��ES6֮ǰ������ֻ��`typeof`������ES6֮�������ֶ������ַ�����   
* **includes()**:����**����ֵ**����ʾ**�Ƿ��ҵ������ַ���**�� 
* **startsWith()**:����**����ֵ**����ʾ�����ַ����Ƿ���ԭ�ַ�����**ͷ��**�� 
* **endsWith()**:����**����ֵ**����ʾ�����ַ����Ƿ���ԭ�ַ�����**β��**�� 
```js
let a = 'hello leo';
a.startsWith('leo');   // false
a.endsWith('o');       // true
a.includes('lo');      // true
```
����������������֧�ֵڶ�����������ʾ��ʼ������λ�á�  
```js
let a = 'hello leo';
a.startsWith('leo',1);   // false
a.endsWith('o',5);       // true
a.includes('lo',6);      // false
```
`endsWith` �����ǰ `n` ���ַ�����������������Դӵ�`n`��λ��ֱ��������  

#### 2.repeat()
`repeat`��������һ�����ַ�������ʾ��ԭ�ַ����ظ�`n`�Ρ�    
**�����÷�**��  
```js
'ab'.repeat(3);        // 'ababab'
'ab'.repeat(0);        // ''
```
**�����÷�**:    
* ����Ϊ`С��`����ȡ��  
```js
'ab'.repeat(2.3);      // 'abab'
```
* ����Ϊ`����`��`Infinity`���򱨴�  
```js
'ab'.repeat(-1);       // RangeError
'ab'.repeat(Infinity); // RangeError
```
* ����Ϊ`0��-1��С��`��`NaN`����ȡ0  
```js
'ab'.repeat(-0.5);     // ''
'ab'.repeat(NaN);      // ''
```
* ����Ϊ`�ַ���`����ת��`����`  
```js
'ab'.repeat('ab');     // ''
'ab'.repeat('3');      // 'ababab'
```

#### 3.padStart(),padEnd()
���ڽ��ַ���**ͷ��**��**β��**��ȫ���ȣ�`padStart()`Ϊ**ͷ����ȫ**��`padEnd()`Ϊ**β����ȫ**��    
��������������**2��**��������һ��ָ��**�ַ�����С����**���ڶ���**���ڲ�ȫ���ַ���**��  
**�����÷�** ��  
```js
'x'.padStart(5, 'ab');   // 'ababx'
'x'.padEnd(5, 'ab');     // 'xabab'
```
**�����÷�**:  
* ԭ�ַ������ȣ����ڻ����ָ����С���ȣ��򷵻�ԭ�ַ�����  
```js
'xyzabc'.padStart(5, 'ab'); // 'xyzabc'
```
* ������ȫ���ַ������Ⱥ�ԭ�ַ�������֮�ͣ�����ָ����С���ȣ����ȥ�������ֵĲ�ȫ�ַ�����  
```js
'ab'.padStart(5,'012345'); // "012ab"
```
* ʡ�Եڶ�������������`�ո�`��ȫ��  
```js
'x'.padStart(4);           // '    x'
'x'.endStart(4);           // 'x    '
```
#### 4.ģ���ַ���
����ƴ���ַ�����ES6֮ǰ��  
```js
let a = 'abc' + 
    'def' + 
    'ghi';
```
ES6֮��  
```js
let a = `
    abc
    def
    ghi
`
```
**ƴ�ӱ���**:
��**������(\`)**��ʹ��`${}`���������򷽷���  
```js
// ES6֮ǰ
let a = 'abc' + v1 + 'def';

// ES6֮��
let a = `abc${v1}def`
```

### �������չ

### ��ֵ����չ
#### 1.Number.isFinite(), Number.isNaN()
`Number.isFinite()` ���ڼ��һ����ֵ�Ƿ������޵ģ�������`Infinity`������������`Number`���ͣ���һ�ɷ���`false` ��    
```js
Number.isFinite(10);            // true
Number.isFinite(0.5);           // true
Number.isFinite(NaN);           // false
Number.isFinite(Infinity);      // false
Number.isFinite(-Infinity);     // false
Number.isFinite('leo');         // false
Number.isFinite('15');          // false
Number.isFinite(true);          // false
Number.isFinite(Math.random()); // true
```

`Number.isNaN()`���ڼ���Ƿ���`NaN`������������`NaN`����һ�ɷ���`false`��  
```js
Number.isNaN(NaN);      // true
Number.isNaN(10);       // false
Number.isNaN('10');     // false
Number.isNaN(true);     // false
Number.isNaN(5/NaN);    // true
Number.isNaN('true' / 0);      // true
Number.isNaN('true' / 'true'); // true
```

**����**��  
�봫ͳȫ�ֵ�`isFinite()`��`isNaN()`���������𣬴�ͳ�����������������Ƚ�����ת����**��ֵ**�����жϡ�    
��ES6������������������ֻ��**��ֵ**��Ч��  `Number.isFinite()`����**����ֵ**һ�ɷ���`false`,` Number.isNaN()`ֻ�ж���`NaN`�ŷ���`true`������һ�ɷ���`false`��  
```js
isFinite(25);          // true
isFinite("25");        // true
Number.isFinite(25);   // true
Number.isFinite("25"); // false

isNaN(NaN);            // true
isNaN("NaN");          // true
Number.isNaN(NaN);     // true
Number.isNaN("NaN");   // false
```

#### 2.Number.parseInt(), Number.parseFloat()
������������ȫ�ַ���`parseInt()`��`parseFloat()`һ�£�Ŀ������**����ȫ���Եķ���**����**���Ը�ģ�黯**��    
```js
parseInt('12.34');     // 12
parseFloat('123.45#'); // 123.45

Number.parseInt('12.34');     // 12
Number.parseFloat('123.45#'); // 123.45

Number.parseInt === parseInt;     // true
Number.parseFloat === parseFloat; // true
```

#### 3.Number.isInteger() 
�����ж�һ����ֵ�Ƿ���������������������ֵ���򷵻�`false`��    
```js
Number.isInteger(10);   // true
Number.isInteger(10.0); // true
Number.isInteger(10.1); // false
```

#### 4.Math�������չ
ES6����17����ѧ��ص�**��̬����**��ֻ����**Math����**�ϵ��á�  
* **Math.trunc**:  
����ȥ��С����С�����֣�**������������**��  
������Ϊ**����ֵ**����**��תΪ��ֵ**��  
������Ϊ**��ֵ**��**�޷���ȡ������ֵ**���򷵻�**NaN**��  
```js
// ����ʹ��
Math.trunc(1.1);     // 1
Math.trunc(1.9);     // 1
Math.trunc(-1.1);    // -1
Math.trunc(-1.9);    // -1
Math.trunc(-0.1234); // -0

// ����Ϊ����ֵ
Math.trunc('11.22'); // 11
Math.trunc(true);    // 1
Math.trunc(false);   // 0
Math.trunc(null);    // 0

// ����Ϊ�պ��޷�ȡ��
Math.trunc(NaN);       // NaN
Math.trunc('leo');     // NaN
Math.trunc();          // NaN
Math.trunc(undefined); // NaN
```
**ES5ʵ��**��   
```js
Math.trunc = Math.trunc || function(x){
    return x < 0 ? Math.ceil(x) : Math.floor(x);
}
```

* **Math.sign()**:  
�ж�һ������**����**��**����**��**����**�����ڷ���ֵ������ת��**��ֵ**��    
����ֵ��   
> ����Ϊ������ ���� +1
> ����Ϊ������ ���� -1
> ����Ϊ0�� ���� 0
> ����Ϊ-0�� ���� -0
> ����Ϊ����ֵ�� ���� NaN
```js
Math.sign(-1);   // -1
Math.sign(1);    // +1
Math.sign(0);    // 0
Math.sign(-0);   // -0
Math.sign(NaN);  // NaN

Math.sign('');   // 0
Math.sign(true); // +1
Math.sign(false);// 0
Math.sign(null); // 0
Math.sign('9');  // +1
Math.sign('leo');// NaN
Math.sign();     // NaN
Math.sign(undefined); // NaN
```

**ES5ʵ��**  
```js
Math.sign = Math.sign || function (x){
    x = +x;
    if (x === 0 || isNaN(x)){
        return x;
    }
    return x > 0 ? 1: -1;
}
```

* **Math.cbrt()**:  
��������һ��������������������Ϊ����ֵ����ת����ֵ��
```js
Math.cbrt(-1); // -1
Math.cbrt(0);  // 0
Math.cbrt(1);  // 1
Math.cbrt(2);  // 1.2599210498

Math.cbrt('1');   // 1
Math.cbrt('leo'); // NaN
```
**ES5ʵ��**  
```js
Math.cbrt = Math.cbrt || function (x){
    var a = Math.pow(Math.abs(x), 1/3);
    return x < 0 ? -y : y;
}
```

* **Math.clz32()**:  
���ڷ���һ������ 32 λ�޷���������ʽ�ж��ٸ�ǰ�� 0��
```js
Math.clz32(0) // 32
Math.clz32(1) // 31
Math.clz32(1000) // 22
Math.clz32(0b01000000000000000000000000000000) // 1
Math.clz32(0b00100000000000000000000000000000) // 2
```

* **Math.imul()**:  
���ڷ����������� 32 λ������������ʽ��˵Ľ�������ص�Ҳ��һ�� 32 λ�Ĵ�����������   
```js
Math.imul(2, 4)   // 8
Math.imul(-1, 8)  // -8
Math.imul(-2, -2) // 4
```

* **Math.fround()**:  
��������һ������**2λ�����ȸ�����**��ʽ��  
```js
Math.fround(0)   // 0
Math.fround(1)   // 1
Math.fround(2 ** 24 - 1)   // 16777215
```

* **Math.hypot()**:   
�����������в�����ƽ���͵�**ƽ����**��  
```js
Math.hypot(3, 4);        // 5
Math.hypot(3, 4, 5);     // 7.0710678118654755
Math.hypot();            // 0
Math.hypot(NaN);         // NaN
Math.hypot(3, 4, 'foo'); // NaN
Math.hypot(3, 4, '5');   // 7.0710678118654755
Math.hypot(-3);          // 3
```

* **Math.expm1()**:  
��������` ex - 1`����`Math.exp(x) - 1`��  
```js
Math.expm1(-1) // -0.6321205588285577
Math.expm1(0)  // 0
Math.expm1(1)  // 1.718281828459045
```
**ES5ʵ��**  
```js
Math.expm1 = Math.expm1 || function(x) {
  return Math.exp(x) - 1;
};
```

* **Math.log1p()**:  
��������`1 + x`����Ȼ��������`Math.log(1 + x)`�����xС��`-1`������`NaN`��  
```js
Math.log1p(1)  // 0.6931471805599453
Math.log1p(0)  // 0
Math.log1p(-1) // -Infinity
Math.log1p(-2) // NaN
```
**ES5ʵ��**  
```js
Math.log1p = Math.log1p || function(x) {
  return Math.log(1 + x);
};
```

* **Math.log10()**:  
���������� `10 `Ϊ�׵�`x�Ķ���`�����xС�� 0���򷵻� `NaN`��  
```js
Math.log10(2)      // 0.3010299956639812
Math.log10(1)      // 0
Math.log10(0)      // -Infinity
Math.log10(-2)     // NaN
Math.log10(100000) // 5
```
**ES5ʵ��**  
```js
Math.log10 = Math.log10 || function(x) {
  return Math.log(x) / Math.LN10;
};
```

* **Math.log2()**:  
���������� `2` Ϊ�׵�`x�Ķ���`�����`x`С��` 0`���򷵻� `NaN`��   
```js
Math.log2(3)       // 1.584962500721156
Math.log2(2)       // 1
Math.log2(1)       // 0
Math.log2(0)       // -Infinity
Math.log2(-2)      // NaN
Math.log2(1024)    // 10
Math.log2(1 << 29) // 29
```
**ES5ʵ��**  
```js
Math.log2 = Math.log2 || function(x) {
  return Math.log(x) / Math.LN2;
};
```
* **˫����������**:  
>`Math.sinh(x)` ����x��**˫������**��hyperbolic sine��
>`Math.cosh(x)` ����x��**˫������**��hyperbolic cosine��
>`Math.tanh(x)` ����x��**˫������**��hyperbolic tangent��
>`Math.asinh(x)` ����x��**��˫������**��inverse hyperbolic sine��
>`Math.acosh(x)` ����x��**��˫������**��inverse hyperbolic cosine��
>`Math.atanh(x)` ����x��**��˫������**��inverse hyperbolic tangent��

#### 5.ָ�������
������ָ�������(`**`):  
```js
2 ** 2; // 4
2 ** 3; // 8 

2 ** 3 ** 2; // �൱�� 2 ** (3 ** 2); ���� 512
```
ָ�������(`**`)��`Math.pow`��ʵ�ֲ���ͬ�������ر��������������߻���ϸ΢�Ĳ��졣
```js
Math.pow(99, 99)
// 3.697296376497263e+197

99 ** 99
// 3.697296376497268e+197
```

### ��������չ
### �������չ

## 2. ES7

## 3. ES8

## 4. ES9

## 5. ֪ʶ����
### �鼶������

ͨ��ָһ��**�����ڲ�**������һ��**������ڲ�**��  
���磺  
```js
function fun1 () {
    // �鼶������
    if (true) {
        // �鼶������
    }
}
```
**ȱ��**��
1.�����ڲ��������������
```js
var a1 = new Date();
function f1 (){
    console.log(a1); // undefined
    if (false) {
        var a1 = 'hello'
    }
}
```
��� `undefined` ����Ϊ `if` �ڵ� `a1` ���������ı��������������ڲ��� `a1` �����ⲿ�� `a1`���������Ϊ `undefined` �� 

2.������ȫ����Ⱦ
```js
var a = 'hello';
for (var i = 0; i< a.length; i++) {
    //...
}
console.log(i); // 5
```
ѭ�������󣬱��� `i` ��ֵ��Ȼ���ڣ���ɱ�����ȫ����Ⱦ��


# �ġ�����