<h1 data-book="builtin_transformer">����ת����</h1>

Rythm�ṩ��һ��������ת��������Ĺ���������ɾ���

<div class="alert alert-info">
<b>ע��</b>�������ر�˵�������е�ת����������<code>Object</code>���͵Ĳ��������仰˵������Խ�ת���������κ����͵Ķ��󣬶���������<code>String</code>���͡������Ƚ�ˬ�� ;-)
</div>

ͨ���������һ����Ҫ�����ִ����͵�ת�����������������͵Ķ��󣬸ö��󽫱���ת��ΪString</code>Ȼ���ڽ���ת�����Ĵ���

### [escape0] ת��

ת����ģ������г��õ�һ�����ܡ�����ͨ�������㶼����Ҫ��ת��ת�����򽻵�����ΪRythm�����ܵ��жϵ�ǰ�����ģ�ѡ����ʵ�ת�巽��������μ�[����](expression#escape)).

#### [escape] escape()

��[**��ǰ**](template_context.md#escape)�����ĵ�ȱʡ������ת����� 

<div class="alert alert-info">
ȱʡ�����Rythm����ת����ʽ��������<code>@foo.escape()</code>��<code>@foo</code>��ͨ������»����һ���Ľ��
</div>

```lang-java,fid-70bccea25d8942b1b87081534d49aa3a
@args Bar bar
@bar.raw()
@bar.escape()
@bar
```

#### [escapeHTML] escapeHTML()

������

* `escapeHtml()`
* `escape("html")`

��[html](http://rythmengine.org/api/org/rythmengine/utils/Escape.html#HTML)��ʽ��ת�����

```lang-java,fid-80a06b8dcfc745ae88d5772b22a56b7a
@args Bar bar
@raw() {
@bar
@bar.escapeHtml()
@bar.escapeHTML()
@bar.escape("html")
}
```

#### [escapeXML]escapeXML()

������

* `escapeXml()`
* `escape("xml")`

��[xml](http://rythmengine.org/api/org/rythmengine/utils/Escape.html#XML)��ת�����

```lang-java,fid-c22f5795355a4e0faaccc3b890026843
@args Bar bar
@raw() {
@bar
@bar.escapeXml()
@bar.escapeXML()
@bar.escape("xml")
}
```

#### [escapeJS]escapeJS()

����

* `escapeJavaScript()`
* `escape("js")`

��[JavaScript](http://rythmengine.org/api/org/rythmengine/utils/Escape.html#JS)��ʽ��ת�����

```lang-java,fid-ec3ccf28950f4b158cde2336632d9429
@args Bar bar
@raw() {
@bar
@bar.escapeJS()
@bar.escapeJavaScript()
@bar.escape("js")
}
```

#### [escapeJSON]escapeJSON()

����

* `escapeJson()`
* `escape("json")`

��[json](http://rythmengine.org/api/org/rythmengine/utils/Escape.html#JSON)��ʽ��ת�����

```lang-java,fid-2c94b9f4c22148b6974dcffbc4bf2214
@args Bar bar
@raw() {
@bar
@bar.escapeJSON()
@bar.escapeJson()
@bar.escape("json")
}
```

#### [escapeCSV]escapeCSV()

����

* `escapeCsv()`
* `escape("csv")`

��[csv](http://rythmengine.org/api/org/rythmengine/utils/Escape.html#CSV)��ʽ��ת�����

```lang-java,fid-51c053ac57644ba9862bae03ee69c2ae
@args Bar bar
@raw() {
@bar
@bar.escapeCSV()
@bar.escapeCsv()
@bar.escape("csv")
}
```

### [format] ��ʽ��

#### [format_number] ��ʽ������

* `format()`
* `format(String pattern)`
* `format(String pattern, Locale locale)`

ʹ��Pattern��Locale����ʽ�����֡�**ע��** ��ת����ֻ������[����](http://docs.oracle.com/javase/6/docs/api/java/lang/Number.html)���ͱ�����

���û��ָ��Locale��Rythm�����[I18N.locale()](http://rythmengine.org/api/org/rythmengine/utils/I18N.html#locale())����ȡ��ֵ����ָ��Pattern������£�Locale������ȡ[DecimalFormatSymbols](http://docs.oracle.com/javase/6/docs/api/java/text/DecimalFormatSymbols.html)������֮�ڹ���һ��[DecimalFormat](http://docs.oracle.com/javase/6/docs/api/java/text/DecimalFormat.html)������û��Pattern�������Locale������ȡһ�� [NumberFormat](http://docs.oracle.com/javase/6/docs/api/java/text/NumberFormat.html)����

```lang-java,fid-9c306f912d4842228bb45a928e89a593
@args Number x, Number y, Number z
[@x]: @x.format()
---
[@y]: @y.format("###,000,000.00")
---
[@z]: @z.format("###,000,000.0000", Locale.SIMPLIFIED_CHINESE)
```

#### [format_date] ��ʽ��ʱ������

* `format()`
* `format(String pattern)`
* `format(String pattern, Locale locale)`
* `format(String pattern, Locale locale, String timezone)`

��pattern, locale��timezone������ʽ��ʱ�����ڱ�����**Note** �ø�ʽ�����߽�������[java.util.Date](http://docs.oracle.com/javase/6/docs/api/java/util/Date.html)����[org.joda.time.DateTime]()���͵ı���.

���û��ָ��Locale��Rythm�����[I18N.locale()](http://rythmengine.org/api/org/rythmengine/utils/I18N.html#locale())����ȡ��ֵ����patternָ���������Locale��������һ��[SimpleDateFormat](http://docs.oracle.com/javase/6/docs/api/java/text/SimpleDateFormat.html)����ʽ������; ���û��ָ��pattern��Rythm��[DateFormat.getDateInstance(DateFormat.Default, locale)](http://docs.oracle.com/javase/6/docs/api/java/text/DateFormat.html#getDateInstance())�������ʽ�������timezoneָ���ˣ���ֵ�������趨���ڸ�ʽ

```lang-java,fid-a1f92368a9a54283af097da64d48676b
@args Date x = new Date()
[@x]: @x.format()
---
[@x]: @x.format("yyyy-MM-dd")
---
[@x]: @x.format(null, Locale.SIMPLIFIED_CHINESE)
---
[@x]: @x.format(null, Locale.US, "GMT")
```

#### [format_currency] ��ʽ������

* `formatCurrency()`
* `formatCurrency(String currencyCode)`
* `formatCurrency(String currencyCode, Locale locale)`

ʹ�û��Ҵ����Locale����ʽ�����ҡ�������ת����`format()`��ͬ, `formatCurrency`����Ҫ�����������������͡����ڷ��������͵ı�����Rythm�����Ƚ���ת��Ϊ�ִ���Ȼ�����`Double.parseDouble`����ȡ����ֵ��**ע��**��`formatCurrency`���ǿ�ֵ��ȫ�ģ�����Ҫʹ��[��ֵ��ȫ��﷨](expression.md#null-safe)�����ϣ���п�ֵ��ȫ��֤��

```lang-java,fid-4af27082ad6d43f3be3e9d81876ea1d3
@args Object o, Number n
[@o]: @o?.formatCurrency()
----
[@n]: @n?.formatCurrency()
```

##### �ο�����

* [http://docs.oracle.com/javase/6/docs/api/java/util/Currency.html](http://docs.oracle.com/javase/6/docs/api/java/util/Currency.html)
* [http://docs.oracle.com/javase/6/docs/api/java/text/NumberFormat.html#getCurrency()](http://docs.oracle.com/javase/6/docs/api/java/text/NumberFormat.html#getCurrency())

### [string] �ִ�����

������ִ������ִ���

#### [capitalizeWords] capitalizeWords()

���ִ��е�ÿ���ֵ�����ĸ��ɴ�д�����������ɷ�������ĸ���ŷָ��

```lang-java,fid-d0eaed51cdb044e3813843845453a819
@args Bar bar, String s
@bar
@bar.capitalizeWords()
------------
@s
@s.capitalizeWords()
```

#### [noAccents] noAccents()

��ת����ͨ�����ڴ���ŷ�����ԡ��÷�ע��������ĸ�����ע�������ĸ��

```lang-java,fid-beacda9f4c7945b7bd743e3da8b4cd7f
@args Bar bar
@bar
@bar.noAccents()
```

#### [lowerFirst] lowerFirst() and capFirst()

���ִ�������ĸ���Сд���ߴ�д��

```lang-java,fid-ae7162075ef5498eb8af84beb8f77b02
@args Bar bar, String s
@bar
@bar.lowerFirst()
---
@s
@s.capFirst()
```

#### [camelCase] camelCase()

���»��߱��ת���շ������`hello_world`���`HelloWorld`

```lang-java,fid-baaa389eae37422b8a48508bd0889fe9
@args Bar bar
@bar
@bar.camelCase()
```

#### [divide] divide()

TBD

#### [lowerCase]lowerCase()

TBD

#### [upperCase]upperCase()

TBD

### [misc]Misc utilities

#### [len]len()

TBD

#### [nl2br] nl2br()

���ִ��еĻ��з����html��`<br/>`��ǩ

```lang-java,fid-e0497048c78248129c13d7b69aa14d52
@args Bar bar
@bar
@bar.nl2br()
```

#### [urlEncode] urlEncode()

ʹ��UTF-8������ִ���urlEncode����

```lang-java,fid-f77daffacf0848bfaa36308b0a4b8804
@args Bar bar
@bar
@bar.urlEncode()
```

#### [i18n] i18n()

���ִ�ȥ���ʻ���Ϣ
Internationalization a string or string of an object

```lang-java,fid-c659f57f6ffd48978b795b244c5b2eeb
@args String x
//-- default locale
@x: @x.i18n()

// -- locale: en
@locale("en"){
@x: @x.i18n()
}

// -- locale: zh_CN
@locale("zh_CN") {
@x: @x.i18n()
}
```

#### [join] join()

* `join()` - join use `,`
* `join(String separator)`
* `join(char separator)`

ʹ��ȱʡ�ָ��`,`����ָ���ָ������һ��[Iterable](http://docs.oracle.com/javase/6/docs/api/java/lang/Iternable.html)���͵ı���

```lang-java,fid-e0497048c78248129c13d7b69aa14d52
@args Bar bar
@bar
@bar.join()
```

### [see] �������

* [���ʽ](template_guide.md#expression)
* [�û�����ת����](user_defined_transformer.md)
* [ת����API](http://rythmengine.org/api/org/rythmengine/extension/Transformer.html)

