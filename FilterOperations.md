# Operations
**Note:** For 0.9.x see [[older version|FilterOperations?version=16]]

All plugins may do following operations to [[entry|Entry]].

```html
<table class="wiki">
<tr>
  <td><strong>Operation</strong></td>
  <td><strong>Effect</strong></td>
</tr><tr>
  <td><div style="color:red; font-weight: bold">Reject</div></td>
  <td>Entry will be permanently removed. Other plugins may not change this status.</td>
</tr><tr>
  <td><div style="color:green; font-weight: bold">Accept</div></td>
  <td>Entry will be marked accepted. Other plugins may still be reject it.</td>
</tr><tr>
  <td><div style="color:#666; font-weight: bold">Undecided</div></td>
  <td>Entry is not marked to any category <i>(default)</i></td>
</tr>
</table>
```

### Represented as a schematic

[[Image(1.0_operations.png)]]

## Scenario

Assuming configuration:


    regexp:
      accept:
        - Something
      reject:
        - CAM


Q: What would happen to file **Something.CAM.XviD**(XXX macro: "BR")
A: It would be rejected, since reject operation is stronger than accept.

Q: What would happen to file **Something.XviD**(XXX macro: "BR")
A: It would be accepted

Q: What would happen to file **Example.XviD**(XXX macro: "BR")
A: It wouldn't be intervened any way, neither accepted nor rejected. Note that output plugins are interested only in accepted entries.
