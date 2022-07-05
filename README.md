# Summer-2022-Web-Analysis-Design

## Initial Domain Model

![Initial](https://www.planttext.com/api/plantuml/svg/XPBTQeGm48NlVOgvBkmR545KkYckBlviUvkcqpKqHZ7PmbBwxaqc5TIRNZbpJcQ-4w9Gt1XumJSZBS9t173cjWSr2gvyvOHqL0g5bQD-xEeY1d_I5MPh7TjJaOtYDg2sCN3bfgzeefyeIWcnzl_bDFQkiEaHtIhZwnticN_nHinoyZvzTmSIBVfnZa59_RcpsE22nI07oWVW8mgAI5JZgIxWIYR0Hg8T6oK0wM80NSrW2fToQE_B3ocunrEYzZuXUIsVhsXz2-zehDHqXcot6VLjs8y702lRl2wJOcdgv9myvTJbht_Mic352CFq4bNQdVAo9I6fqoExXF4Bo_8gg5t6Ahzb-JaU3eVDAqQ_)

```plantuml
class Website {
  Path localPath
  Collection<URL> siteURLs
  Collection<HTMLDocument> allPages
}

Class HTMLDocument {
  Path localPath
  Collection<StyleSheet> styles
  Collection<JavaScript> scripts
  Collection<Anchor> links
  Collection<Image> images
  
}

class Stylesheet {

}

class Script {

}

class Image {

}

class Anchor {
    URI path
    Classification linkType
    TargetType destinationType
}

enum Classification {
    INTERNAL
    INTRAPAGE
    EXTERNAL
}

enum TargetType {
    HTMLDOCUMENT
    ARCHIVE
    VIDEO
    AUDIO
}

Website *-- HTMLDocument
```

---

## Adding Analysis

```plantuml
class Website {
  Path localPath
  Collection<URL> siteURLs
  Collection<HTMLDocument> allPages
}

Class HTMLDocument {
  Path localPath
  Collection<StyleSheet> styles
  Collection<JavaScript> scripts
  Collection<Anchor> links
  Collection<Image> images
  
}

class Stylesheet {

}

class Script {

}

class Image {

}

class Anchor {
    URI path
    Classification linkType
    TargetType destinationType
}

enum Classification {
    INTERNAL
    INTRAPAGE
    EXTERNAL
}

enum TargetType {
    HTMLDOCUMENT
    ARCHIVE
    VIDEO
    AUDIO
}

class DocumentParser {

}

class WebsiteWalker {

}

class ExcelWriter {

}

class JSONWriter {

}

class TextWriter {

}

Website *-- HTMLDocument
DocumentParser -->"populates" HTMLDocument
```
