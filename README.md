```
Input: model.xml
Output: Templates
1:	Templates, Locations, Transitions[]
2:	transitionId, templateId1
3:	for template[0] to template[n] do
4:		for location[0] to location[n] do
5: 			Locations.append(location[i])
6: 		end for
7:		for transition[0] to transition[n] do
8:			Transitions.append(template[i])
9:		end for
10:		Templates.append(template[i])
11:	end for
12:	return Templates

 ```
