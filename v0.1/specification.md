---
title: v0.1 Specification [WIP]
---

## Preamble 

This specification (pageXML v0.1) is a draft guideline designed to serve as a base for various evolutions and expansions of the outlined ideas.

This specification should be interpreted as according to British English, and is spelt as such. It is reccomended you have a working knowledge of (X)HTML and XML, to understand the document. PageXML is based off of XML.

Any questions about this specifcation can be raised by writing an [issue on Github](https://github.com/isaacrg/pagexml/issues).

## Implementing the standard.

When embedded within an HTML document, PageXML documents should be wrapped within a `<pagexml-container>` tag. Within a PageXML document use the file extension `.pagexml`, which should be wrapped within `<pagexml>` tags.


PageXML supports multiple pages, which are contained within `<page>` tags. They can be given a unqiue id with the `id` attribute. They can also be given a title with the `title` attribute. It is reccomended that the page which is going to be loaded first is give the id "main". Each page is made up of two sub-sections, the `<meta>` and `<content>` sections. The `<meta>` section allows for metadata declaration. The `<content>` section allows for content to be declared using a limited HTML standard, though other format types are supported via the use of the `type` attribute. 

Separate parts to an HTML page can be created using the `<part>` tag with a given id, and can then displayed using the `<use>` tag, setting the `part-id` attribute to be the same as the `<part>` you wish to import.

Links between internal pages can be created by using the `<a>` tag, with the `internal-page` attribute set to the id of the page you wish to use.

## Examples

### Hello World

`{% highlight xml %}
<pagexml>
  <page id="main" title="Hello World">
    <content>
      <h1>Hello World</h1>
      <p>Does this sound familiar?</p>
    </content>
  </page>
</pagexml>
{% endhighlight %}`
