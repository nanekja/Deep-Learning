
## 1) What are Channels and Kernels ?

### Answer:

Kernels are unique individual basic building blocks of an image. 
These are also called as feature extractor as they constitute unique feature of an image. 
Some examples are vertical edges or horizontal edges.

Channels are a group of kernels of the same type that is if we group all vertical edges, we call it a vertical edge channel. 
The number of channels is also proportional to number of kernels or number of Unique features that can be extracted from an image.



## 2) Why should we only (well mostly) use 3x3 Kernels?

### Answer:

3x3 Kernels are determined to be optimized choice by Nvidia and other companies and hence works well with GPU's. Another intuition to think of is that the smaller the kernel is the more focused feature we can obtain as it is derived from smaller area of the i/p thus allowing capture of more details for the o/p.



## 3) How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations) ?

### Answer:

Convolution by 3x3 kernel operation will reduce 2 pixel dimension in the output layer and following is the calculation which leads to 1 x 1 o/p after 99 layers.

**I/P Layer   Kernel  O/P Layer**
199 x 199 | 3 x 3 | 197 x 197
197 x 197 | 3 x 3 | 195 x 195
195 x 195 | 3 x 3 | 193 x 193
193 x 193 | 3 x 3 | 191 x 191
191 x 191 | 3 x 3 | 189 x 189
189 x 189 | 3 x 3 | 187 x 187
187 x 187 | 3 x 3 | 185 x 185
185 x 185 | 3 x 3 | 183 x 183
183 x 183 | 3 x 3 | 181 x 181
181 x 181 | 3 x 3 | 179 x 179
179 x 179 | 3 x 3 | 177 x 177
177 x 177 | 3 x 3 | 175 x 175
175 x 175 | 3 x 3 | 173 x 173
173 x 173 | 3 x 3 | 171 x 171
171 x 171 | 3 x 3 | 169 x 169
169 x 169 | 3 x 3 | 167 x 167
167 x 167 | 3 x 3 | 165 x 165
165 x 165 | 3 x 3 | 163 x 163
163 x 163 | 3 x 3 | 161 x 161
161 x 161 | 3 x 3 | 159 x 159
159 x 159 | 3 x 3 | 157 x 157
157 x 157 | 3 x 3 | 155 x 155
155 x 155 | 3 x 3 | 153 x 153
153 x 153 | 3 x 3 | 151 x 151
151 x 151 | 3 x 3 | 149 x 149
149 x 149 | 3 x 3 | 147 x 147
147 x 147 | 3 x 3 | 145 x 145
145 x 145 | 3 x 3 | 143 x 143
143 x 143 | 3 x 3 | 141 x 141
141 x 141 | 3 x 3 | 139 x 139
139 x 139 | 3 x 3 | 137 x 137
137 x 137 | 3 x 3 | 135 x 135
135 x 135 | 3 x 3 | 133 x 133
133 x 133 | 3 x 3 | 131 x 131
131 x 131 | 3 x 3 | 129 x 129
129 x 129 | 3 x 3 | 127 x 127
127 x 127 | 3 x 3 | 125 x 125
125 x 125 | 3 x 3 | 123 x 123
123 x 123 | 3 x 3 | 121 x 121
121 x 121 | 3 x 3 | 119 x 119
119 x 119 | 3 x 3 | 117 x 117
117 x 117 | 3 x 3 | 115 x 115
115 x 115 | 3 x 3 | 113 x 113
113 x 113 | 3 x 3 | 111 x 111
111 x 111 | 3 x 3 | 109 x 109
109 x 109 | 3 x 3 | 107 x 107
107 x 107 | 3 x 3 | 105 x 105
105 x 105 | 3 x 3 | 103 x 103
103 x 103 | 3 x 3 | 101 x 101
101 x 101 | 3 x 3 |  99 x  99
	99 x 99 | 3 x 3 | 97 x 97
	97 x 97 | 3 x 3 | 95 x 95
	95 x 95 | 3 x 3 | 93 x 93
	93 x 93 | 3 x 3 | 91 x 91
	91 x 91 | 3 x 3 | 89 x 89
	89 x 89 | 3 x 3 | 87 x 87
	87 x 87 | 3 x 3 | 85 x 85
	85 x 85 | 3 x 3 | 83 x 83
	83 x 83 | 3 x 3 | 81 x 81
	81 x 81 | 3 x 3 | 79 x 79
	79 x 79 | 3 x 3 | 77 x 77
	77 x 77 | 3 x 3 | 75 x 75
	75 x 75 | 3 x 3 | 73 x 73
	73 x 73 | 3 x 3 | 71 x 71
	71 x 71 | 3 x 3 | 69 x 69
	69 x 69 | 3 x 3 | 67 x 67
	67 x 67 | 3 x 3 | 65 x 65
	65 x 65 | 3 x 3 | 63 x 63
	63 x 63 | 3 x 3 | 61 x 61
	61 x 61 | 3 x 3 | 59 x 59
	59 x 59 | 3 x 3 | 57 x 57
	57 x 57 | 3 x 3 | 55 x 55
	55 x 55 | 3 x 3 | 53 x 53
	53 x 53 | 3 x 3 | 51 x 51
	51 x 51 | 3 x 3 | 49 x 49
	49 x 49 | 3 x 3 | 47 x 47
	47 x 47 | 3 x 3 | 45 x 45
	45 x 45 | 3 x 3 | 43 x 43
	43 x 43 | 3 x 3 | 41 x 41
	41 x 41 | 3 x 3 | 39 x 39
	39 x 39 | 3 x 3 | 37 x 37
	37 x 37 | 3 x 3 | 35 x 35
	35 x 35 | 3 x 3 | 33 x 33
	33 x 33 | 3 x 3 | 31 x 31
	31 x 31 | 3 x 3 | 29 x 29
	29 x 29 | 3 x 3 | 27 x 27
	27 x 27 | 3 x 3 | 25 x 25
	25 x 25 | 3 x 3 | 23 x 23
	23 x 23 | 3 x 3 | 21 x 21
	21 x 21 | 3 x 3 | 19 x 19
	19 x 19 | 3 x 3 | 17 x 17
	17 x 17 | 3 x 3 | 15 x 15
	15 x 15 | 3 x 3 | 13 x 13
	13 x 13 | 3 x 3 | 11 x 11
	11 x 11 | 3 x 3 |	9 x  9
		9 x 9  | 3 x 3 |	7 x  7
 		7 x 7  | 3 x 3 |	5 x  5
 		5 x 5  | 3 x 3 |	3 x  3
 		3 x 3  | 3 x 3 |	1 x  1

#####################################################################



