## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/fgpeixo/fgpeixo.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

LOOP AT it_zdemo INTO wa_zdemo.
* Avoid duplicate entries for key field Vendor.
READ TABLE <gfs_dyn_table> INTO <gfs_line1> WITH KEY (‘VEND’) = wa_zdemo-vend.
IF sy-subrc = 0.
*if <gfs_line1> is ASSIGNED.
*  UNASSIGN <gfs_line1>.
CONTINUE.
ENDIF.

ASSIGN COMPONENT ‘VEND’ OF STRUCTURE <gfs_line> TO <fs1>.
*if <fs1> is ASSIGNED.
<fs1> = wa_zdemo-vend.
UNASSIGN <fs1>.
**endif.

LOOP AT gt_component INTO ls_component.
IF ls_component-name = ‘VEND’.
CONTINUE.
ENDIF.
READ TABLE it_zdemo WITH KEY vend = wa_zdemo-vend month = ls_component-name INTO wa_zdemo1.
IF sy-subrc = 0.
ASSIGN COMPONENT ls_component-name OF STRUCTURE <gfs_line> TO <fs1>.
IF <fs1> IS ASSIGNED.
<fs1> = wa_zdemo1-amt.
UNASSIGN <fs1>.
ENDIF.
ENDIF.
CLEAR : wa_zdemo1.
ENDLOOP.
APPEND <gfs_line> TO <gfs_dyn_table>.
CLEAR: <gfs_line>.
CLEAR: wa_zdemo, wa_zdemo1.
ENDLOOP.

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/fgpeixo/fgpeixo.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
