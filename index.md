---
title: ABAP Development 
---

Development Diary about ABAP development containing a range of blog posts from quick tips and tricks to in depth articles.

For in depth article, please follow the links below. Blog posts can be found in the lower part of the page.

[ABAP](ABAP.md)|[Tools](tools.md)|[Cheatsheets](cheatsheets.md)|[Resources](resources.md)

# Topics to explore as TIL
- CDS
- RAP
- ADT
- Fiori Elements
- Algorithms
- Pointer to other repo's
- Cryptography

```abap
DATA(test) = conv char( 't' ).

DATA(business_partner) = new zcl_business_partner( '1000054320' ).
if business_partner->exists( ).
  "Do something
endif.
```



