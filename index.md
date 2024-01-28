---
title: Home 
---

This is my blog about ABAP development containing a range of posts from quick tips and tricks to in depth articles.

For in depth articles, please follow the links above. Blog posts can be found below.

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



