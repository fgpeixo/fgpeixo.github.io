```ABAP
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
```
