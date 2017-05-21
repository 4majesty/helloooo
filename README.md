```
Input: exp
Output: tree
1:	treeBinaryTree('')
2:	stack""
3:	num0
4:	symbols['!', '&', '|', '^']
5: 	containFalse
6: 	for s in symbols do
7:		if exp.__contains__(s)
8:		then containTrue
9:		end if
10:  end for
11:  if not contain then
12:		tree.dataexp
13:		return tree
14:	end if
15:	for i in exp do
16:		if i = '(' then
17:			numnum + 1
18:			stackstack + i
19:		else if i = ')' then
20:			numnum - 1
21:			stackstack + i
22:	    else if num = 0 and symbols.__contains__(i) then
23:			if i = '!' then
24:				tree.datai
25:				stackexp[1:]
26: 				if stack[0] = '(' then
27:					stackstack[1:-1]
28:				tree.insertLeft('')
29:				tree.insertRight(buildexpressionTree(stack))
30:				return tree
31:			else then
32:				tree.datai
33:				print i
34:				if stack[0] = '(' then
35:					leftStackstack[1:-1]
36:					else then leftStackstack
37:				end if
38:				tree.insertLeft(buildexpressionTree(leftStack))
39:				rightStackexp[len(stack):]
40:				rightStackrightStack[1:]
41:				if rightStack[0] = '(' then
42:					rightStackrightStack[1:-1]
43:				end if
44:				tree.insertRight(buildexpressionTree(rightStack))
45:				return tree
46:			end if
47:		else stackstack + i
48:		end if
49:	end for

 ```
