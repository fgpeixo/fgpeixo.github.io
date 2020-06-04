# Resources Page

## ABAP
- Parallel Processing
      [SPTA Framework](http://mysapbook.blogspot.co.uk/2013/12/spta-framework-parallel-processing.html)
      Check program SPAT_PARA_DEMO_1

- Dynamic Programming

```abap
data: lt_key_components type abap_component_tab,
      lt_keys           type ref to data.

field-symbols:
    <lt_keys> type any table.

data(lr) =  cast cl_abap_structdescr( cl_abap_elemdescr=>describe_by_name( exporting p_name = '/BFH/INTERFACE' ) ).

"Get DDIC fields list to check which fields are keys
data(lt_ddic_field_list) = lr->get_ddic_field_list( ).
"Get components to create a new structure with only key fields
data(lt_components) = lr->get_components( ).

"Keep only key fields and create new structure
delete lt_ddic_field_list where keyflag is initial.
loop at lt_ddic_field_list into data(ls_ddic_field).
  try.
      append lt_components[ name = ls_ddic_field-fieldname ] to lt_key_components.
    catch cx_sy_itab_line_not_found.
  endtry.
endloop.

data(lr_key_str) = cl_abap_structdescr=>get( exporting p_components = lt_key_components ).
data(lr_key_table) = cl_abap_tabledescr=>get( exporting p_line_type = lr_key_str ).

check lr_key_table is bound.
create data lt_keys type handle lr_key_table.
assign lt_keys->* to <lt_keys>.
```

## SAPUI5

## Algorithms

- [Coursera - Algorithms Part I - Princeton University](https://www.coursera.org/learn/algorithms-part1)
- [Coursera - Algorithms Part II - Princeton University](https://www.coursera.org/learn/algorithms-part2)

## Git
- Git-aware prompt
 - Windowns - posh-git
 - Linux - bash-git-prompt
 - X-Plat - starship

[link_test](./link_test.md)
