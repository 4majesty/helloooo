```python
def parseXML(root):
    templates = []
    transitionid = 1
    for templatexml in root.getiterator("template"):
        declaration = templatexml.findtext("declaration") or ""
        autoname = templatexml.findtext("name") or ""
        transitions = []
        for transitionxml in templatexml.getiterator("transition"):
            sourceL = transitionxml.find('source').get('ref')
            targetL = transitionxml.find('target').get('ref')
            transition = Transition(transitionid, sourceL, targetL, )
            transitionid = transitionid + 1
            for labelxml in transitionxml.getiterator("label"):
                """if labelxml.get('kind') in ['guard','assignment']
					label = getattr(transition, labelxml.get('kind'))
					label.value = labelxml.text"""
                if labelxml.get('kind') == 'guard':
                    transition.guard = labelxml.text
                if labelxml.get('kind') == 'assignment':
                    transition.assignment = labelxml.text
            transitions += [transition]
        locations = []
        for locationxml in templatexml.getiterator("location"):
            name = locationxml.findtext("name")
            location = Location(id=locationxml.get('id'), name=name, transitions=transitions)
            location.name = autoname + "." + location.name
            for labelxml in locationxml.getiterator("label"):
                if labelxml.get('kind') == 'invariant':
                    location.invariant = labelxml.text
            locations += [location]
        if templatexml.find("init") != None:
            initlocation = templatexml.find("init").get('ref')
            for l in locations:
                if l.id == templatexml.find("init").get('ref'):
                    l.init = True
        else:
            initlocation = None
        template = Template(templatexml.find("name").text, declaration, locations=locations, initlocation=initlocation,
                            transitions=transitions)
        templates += [template]
    return templates
 ```
