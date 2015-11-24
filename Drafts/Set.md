# Set 2.0


    set:
      [FIELD_NAME]: <string format>
    
      [[        {value|FIELD_NAME]:]]: <string format>
        [regexp]: <regexp groups>
        [[[<regexp what>, <with text>|replace]:]]

**Simple example:**


    set:
      path: /foo/bar/%(series_name)s/


**Advanced example:**


    set:
      path:
        value: /foo/bar/%(series_name)s/
        replace: [[', '.'|']]

