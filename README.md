# nonext-todo.txt
Todo.sh plugin for seeing which of your projects (listed in one or more project files) have no next action in `todo.txt`.

By default, project files are `projects.txt` and any file ending in `.prj.txt`. Projects are identified as words beginning in `+` followed by alphanumeric characters or `_`, `-`, or `.`. Other items are ignored. Priority tags can be preceded by whitespace, which a organizing your projects in an outline form. All other items are ignored.

For each project tag, `+project`, in any of your project files that do not have a corresponding tagged task in `todo.txt`, an item will be added to `todo.txt`. 

Usage: `todo.sh nonext`

## Example
```
$ cat -n  test.prj.txt
     1  # personal
     2  Walk dog
     3          (B) +adopt-puppy
     4          (B) +buy-leash
     5  
     6  # work
     7  (A) +tps-report *use new coversheet*
     
$ t nonext
1 (B) +adopt-puppy file:test.prj.txt Choose Next Action
TODO: 1 added.
2 (B) +buy-leash file:test.prj.txt Choose Next Action
TODO: 2 added.
3 (A) +tps-report file:test.prj.txt Choose Next Action
TODO: 3 added.
03 (A) +tps-report
01 (B) +adopt-puppy
02 (B) +buy-leash
--
TEST: 3 of 3 projects have no next action

$ t ls
3 (A) +tps-report file:test.prj.txt Choose Next Action
1 (B) +adopt-puppy file:test.prj.txt Choose Next Action
2 (B) +buy-leash file:test.prj.txt Choose Next Action
--
TODO: 3 of 3 tasks shown

```
