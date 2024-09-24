---(bool)
 <p>The product of 6 and 7 is 42.</p>
<p>The product of 7 and 6 is 42.</p>

https://www.instagram.com/p/CxOWiQNP2MO/
https://youtube.com/@luleluckyboy307?si=aimZr1XXm5ojqyX1
{{< instagram CxOWiQNP2MO >}}
[Post 1]({{% relref "/posts/post-1" %}})
[Post 1]({{% relref "/posts/post-1.md" %}})
[Post 1]({{% relref "/posts/post-1#foo" %}})
[Post 1]({{% relref "/posts/post-1.md#foo" %}})
Rendered:

<a href="/posts/post-1/">Post 1</a>
<a href="/posts/post-1/">Post 1</a>
<a href="/posts/post-1/#foo">Post 1</a>
<a href="/posts/post-1/#foo">Post 1<
https://x.com/SanDiegoZoo/status/1453110110599868418
Include this in your Markdown:

{{< twitter user="SanDiegoZoo" id="1453110110599868418" >}}


title: transform.HighlightCodeBlock
description: Highlights code received in context within a code block render hook.
categories: []
keywords: []
action:
  aliases: []
  related:
    - functions/transform/CanHighlight
    - functions/transform/Highlight
  returnType: highlight.HighlightResult 
  signatures: ['transform.HighlightCodeBlock CONTEXT [OPTIONS]']
---

This function is only useful within a code block render hook.

Given the context passed into a code block render hook, `transform.HighlightCodeBlock` returns a `HighlightResult` object with two methods.

.Wrapped
: (`template.HTML`) Returns highlighted code wrapped in `<div>`, `<pre>`, and `<code>` elements. This is identical to the value returned by the transform.Highlight function.

.Inner
: (`template.HTML`) Returns highlighted code without any wrapping elements, allowing you to create your own wrapper.

```go-html-template
{{ $result := transform.HighlightCodeBlock . }}
{{ $result.Wrapped }}
```

To override the default [highlighting options]:

```go-html-template
{{ $opts := merge .Options (dict "linenos" true) }}
{{ $result := transform.HighlightCodeBlock . $opts }}
{{ $result.Wrapped }}
```

[highlighting options]: /functions/transform/highlight/#options
