```python
class Template:
    def __init__(self, name, declaration="", locations=None, initlocation=None, transitions=None):
        self.name = name
        self.declaration = declaration
        self.locations = locations or []
        self.initlocation = initlocation
        self.transitions = transitions or []
 ```
