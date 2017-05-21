```python
class Location:
    def __init__(self, id, name=None, invariant=None, init=False, transitions=[]):
        self.id = id
        self.name = name
        self.invariant = invariant
        self.init = init
        self.next = self.initNexttransition(transitions) or {}

    def initNexttransition(self, transitions):
        nexttr = {}
        for tr in transitions:
            if tr.source == self.id:
                nexttr[tr.id] = False
        return nexttr

    def getlocation(self):
        return [self.id, self.name, self.invariant, self.init, self.next]


class Transition:
    def __init__(self, id, source, target, guard=None, assignment=None):
        self.id = id
        self.source = source
        self.target = target
        self.guard = guard
        self.assignment = assignment

    def gettransition(self):
        return [self.id, self.source, self.target, self.guard, self.assignment]
 ```
