# Builtin Transformers

Rythm provides a set of built-in [transformers](expression.md#transformer) to easy your work

<div class="alert alert-info">
<b>Note</b>, unless specified, all built-in transformers apply to <code>Object</code> type. In other words, you are use them to transform variable of any type, not only <code>String</code>s. 
</div>

If a variable been transformed is not a <code>String</code>, then it will be converted to <code>String</code> via [S.str(Object)](http://rythmengine.org/api/com/greenlaw110/rythm/utils/S.html#str(java.lang.Object)) call 

### [escape]Escaping

Use escaping transformers when needed. (Usually you don't need to as Rythm is intelligent enough to escape your emissions with property escape scheme. Check it out at [here](expression#escape)).

#### escape()

Emit expression using the [**current**](template_context.md#escape) escape scheme. 

<div class="alert alert-info">
Since Rythm always escape expression output, meaning <code>@foo.escape()</code> has exactly the same effect of <code>@foo</code>.
</div>

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-70bccea25d8942b1b87081534d49aa3a
@args Bar bar
@bar.raw()
@bar.escape()
@bar
```

#### escapeHTML()

Alias:

* `escapeHtml()`
* `escape("html")`

Emit expression using the [html](http://rythmengine.org/api/com/greenlaw110/rythm/utils/Escape.html#HTML) escape scheme.

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-80a06b8dcfc745ae88d5772b22a56b7a
@args Bar bar
@raw() {
@bar
@bar.escapeHtml()
@bar.escapeHTML()
@bar.escape("html")
}
```

#### escapeXML()

Alias:

* `escapeXml()`
* `escape("xml")`

Emit expression using the [xml](http://rythmengine.org/api/com/greenlaw110/rythm/utils/Escape.html#XML) escape scheme.

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-c22f5795355a4e0faaccc3b890026843
@args Bar bar
@raw() {
@bar
@bar.escapeXml()
@bar.escapeXML()
@bar.escape("xml")
}
```

#### escapeJS()

Alias:

* `escapeJavaScript()`
* `escape("js")`

Emit expression using the [js](http://rythmengine.org/api/com/greenlaw110/rythm/utils/Escape.html#JS) escape scheme.

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-ec3ccf28950f4b158cde2336632d9429
@args Bar bar
@raw() {
@bar
@bar.escapeJS()
@bar.escapeJavaScript()
@bar.escape("js")
}
```

#### escapeJSON()

Alias:

* `escapeJson()`
* `escape("json")`

Emit expression using the [json](http://rythmengine.org/api/com/greenlaw110/rythm/utils/Escape.html#JSON) escape scheme.

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-2c94b9f4c22148b6974dcffbc4bf2214
@args Bar bar
@raw() {
@bar
@bar.escapeJSON()
@bar.escapeJson()
@bar.escape("json")
}
```

#### escapeCSV()

Alias:

* `escapeCsv()`
* `escape("csv")`

Emit expression using the [csv](http://rythmengine.org/api/com/greenlaw110/rythm/utils/Escape.html#CSV) escape scheme.

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-51c053ac57644ba9862bae03ee69c2ae
@args Bar bar
@raw() {
@bar
@bar.escapeCSV()
@bar.escapeCsv()
@bar.escape("csv")
}
```

### String operations

Use string operation transformers to manupulate the output string.

#### capitalizeWords()

Captialize the first character of each words. Words are separated by non digits-alphabetic characters.

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-d0eaed51cdb044e3813843845453a819
@args Bar bar, String s
@bar
@bar.capitalizeWords()
------------
@s
@s.capitalizeWords()
```

#### noAccents()

Replace accent character (usually found in European languages) with corresponding non-accent character

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-beacda9f4c7945b7bd743e3da8b4cd7f
@args Bar bar
@bar
@bar.noAccents()
```

#### lowerFirst() and capFirst()

Make the first letter of the object to be lowercase or uppercase

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-ae7162075ef5498eb8af84beb8f77b02
@args Bar bar, String s
@bar
@bar.lowerFirst()
---
@s
@s.capFirst()
```

#### camelCase()

Change each word from underscore style to camel case style

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-baaa389eae37422b8a48508bd0889fe9
@args Bar bar
@bar
@bar.camelCase()
```

### Format

#### Format Number: format(), format(String pattern), format(String pattern, Locale locale)

format a number using pattern and locale. **Note** this transformer only applies to [java.lang.Number](http://docs.oracle.com/javase/6/docs/api/java/lang/Number.html) type variable.

If locale is not specified, then a call to [com.greenlaw110.rythm.utils.I18N.locale()](http://rythmengine.org/api/com/greenlaw110/rythm/utils/I18N.html#locale()) is used to fetch the locale. If pattern is specified, the locale is used to get the [java.text.DecimalFormatSymbols](http://docs.oracle.com/javase/6/docs/api/java/text/DecimalFormatSymbols.html) to construct the [java.text.DecimalFormat](http://docs.oracle.com/javase/6/docs/api/java/text/DecimalFormat.html) object, otherwise, the locale is used to get [java.text.NumberFormat](http://docs.oracle.com/javase/6/docs/api/java/text/NumberFormat.html) object.

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-9c306f912d4842228bb45a928e89a593
@args Number x, Number y, Number z
[@x]: @x.format()
---
[@y]: @y.format("###,000,000.00")
---
[@z]: @z.format("###,000,000.0000", Locale.SIMPLIFIED_CHINESE)
```


### Misc utilities

#### nl2br()

Change line break to html `<br/>` element

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-e0497048c78248129c13d7b69aa14d52
@args Bar bar
@bar
@bar.nl2br()
```

#### urlEncode()

Encode URL using UTF-8

##### <i class="icon-magic"></i> Try yourself

```lang-java,fid-xxxx
@args Bar bar
@bar
@bar.urlEncode()
```
