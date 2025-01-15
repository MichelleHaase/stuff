# standart Markdown Cheatsheet

* header are defined with Hashes the more hashes the lower the header ranks
* bullet points are created with asterisks
* writing *stuff* italic is done by encasing it in one pair of asterisks
* writing **stuff** bold is done by encasing it in two pairs of asterisks
* to enforce a line break there needs to be trailing whitespace before the break
```
three back ticks create a codeblock and three more closes it
writing the language name directly after the first three ticks creates syntax highlighting 
```
```python
def main():
    a = int(input("What's a? ").strip())
    b = int(input("What's b? ").strip())
    print(f"c={a+b}")
```