```
Algorithm fedtomatrix ()
Input: federation, clock
Output: matrix
1:	matrix  []
2:	for i in clocks do
3: 	    line  []
4:		for j in clocks do
5: 	    	if i = j or i = 'x0' then
6: 				line.append(Relation(0, '<='))
7:			else line.append(Relation(sys.maxint / 2, '<='))
8:			end if
9:		end for
10:		matrix.append(line)
11:	end for
12:	federation = federation.replace(' ', ' ') .replace('(', ' ') .replace(')', ' ') .replace('v.', ' ')
13:	expressions = federation.split('&')
14:	for exp in expressions do
15:		if '-' in exp and exp.index('-') is not 0 then
16:			splitexp, constraint  splitjudgement(exp)
17:			exsistclocks  splitexp[0].split('-')
18:			index0  clocks.index(exsistclocks[0])
19:			index1  clocks.index(exsistclocks[1])
20:			if constraint = '==' then
21:				constraint  '<='
22:				matrix[index0][index1]  Relation(int(splitexp[-1]), constraint)
23:				matrix[index1][index0]  Relation(0 - int(splitexp[-1]), constraint)
24:			else then
25:				matrix[index0][index1]  Relation(int(splitexp[-1]), constraint)
26:			else then
27:				splitexp, constraint  splitjudgement(exp)
28:				# whether is x==y
29:				if splitexp[0] in clocks and splitexp[-1] in clocks then
30:					index0  clocks.index(splitexp[0])
31:					index1  clocks.index(splitexp[-1])
32:					matrix[index0][index1]  Relation(0, '<=')
33:					matrix[index1][index0]  Relation(0, '<=')
34:					continue
35:				end if
36:				# value is in the left and clock in the right
37:				if splitexp[0] not in clocks then
38:					value  splitexp[0]
39:					index0  0
40:					index1  clocks.index(splitexp[-1])
41:					matrix[index0][index1]  Relation(0 - int(value), constraint)
42:				else then
43:					value  splitexp[-1]
44:					index0  clocks.index(splitexp[0])
45:					index1  0
46:					if constraint = '==' then
47:						constraint  '<='
48:						matrix[index0][index1]  Relation(int(value), constraint)
49:						matrix[index1][index0]  Relation(0 - int(value), constraint)
50:						else matrix[index0][index1]  Relation(int(value), constraint)
51: 					end if
52:				end if
53:			end if
54:		end if
55:	end for
56:	# Floyd - Warshall algorithm get remaining values
57:	k  0
58:	while k < len(clocks):
59:	i  0
60:		while i < len(clocks):
61:			j  0
62:			while j < len(clocks) do
63:				if matrix[i][j].value >= matrix[i][k].plus(matrix[k][j]).value then
64:					matrix[i][j]  matrix[i][k].plus(matrix[k][j])
65:				end if
66:				j += 1
67:			i += 1
68:		k += 1
69:	return matrix

 ```
