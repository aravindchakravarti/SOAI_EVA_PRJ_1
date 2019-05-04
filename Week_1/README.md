# What are Channels and Kernels?
  1. Kernels are the feature extractors. Image is a very complicated (kind of mathematical function) which is made of lots and lots of **edge types**. Now in order to extract these **Edges** we need a *Feature Extractors* which we are going to call as **Kernels**
  2. Channels are the one who contain similar features. For e.g., a channel may contain all **Red** pixels of an image, a channel may contain all **Horizontal edges** of an image
  
## Side note:
Some time it is confusing that even 'Kernels' contain channels (For example if input shape is 100 x 100 x 64 then our kernel will be of the shape 3 x 3 x 64 x n) These channels should not be confused with output channels. The channels of Kernels are just integrated part of feature extractors

# Why we should mostly use 3x3 Kernels?
  1. Okay. Let us say we need to have 11x11 kernel, then we know that by using 3x3 | 3x3 | 3x3 | 3x3 | 3x3  we get same effect of 11x11. 
  2. Using multiple 3x3 (as shown above) makes these small kernels to *Learn* building blocks of complex Features rather than just those featuers
  3. Most of the GPUs are optimized for 3x3. Hence GPU is going to run faster if we use 3x3
  
# How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)
One line answer 199/2 = Roughly 100 layers.
*Lets do it*
199 x 199 | 3x3 = 197 x 197  
197 x 197 | 3x3 = 195 x 195  
195 x 195 | 3x3 = 193 x 193  
193 x 193 | 3x3 = 191 x 191  
191 x 191 | 3x3 = 189 x 189  
189 x 189 | 3x3 = 187 x 187  
187 x 187 | 3x3 = 185 x 185  
185 x 185 | 3x3 = 183 x 183  
183 x 183 | 3x3 = 181 x 181  
181 x 181 | 3x3 = 179 x 179  
179 x 179 | 3x3 = 177 x 177  
177 x 177 | 3x3 = 175 x 175  
175 x 175 | 3x3 = 173 x 173  
173 x 173 | 3x3 = 171 x 171  
171 x 171 | 3x3 = 169 x 169  
169 x 169 | 3x3 = 167 x 167  
167 x 167 | 3x3 = 165 x 165  
165 x 165 | 3x3 = 163 x 163  
163 x 163 | 3x3 = 161 x 161  
161 x 161 | 3x3 = 159 x 159  
159 x 159 | 3x3 = 157 x 157  
157 x 157 | 3x3 = 155 x 155  
155 x 155 | 3x3 = 153 x 153  
153 x 153 | 3x3 = 151 x 151  
151 x 151 | 3x3 = 149 x 149  
149 x 149 | 3x3 = 147 x 147  
147 x 147 | 3x3 = 145 x 145  
145 x 145 | 3x3 = 143 x 143  
143 x 143 | 3x3 = 141 x 141  
141 x 141 | 3x3 = 139 x 139  
139 x 139 | 3x3 = 137 x 137  
137 x 137 | 3x3 = 135 x 135  
135 x 135 | 3x3 = 133 x 133  
133 x 133 | 3x3 = 131 x 131  
131 x 131 | 3x3 = 129 x 129  
129 x 129 | 3x3 = 127 x 127  
127 x 127 | 3x3 = 125 x 125  
125 x 125 | 3x3 = 123 x 123  
123 x 123 | 3x3 = 121 x 120  
121 x 121 | 3x3 = 119 x 119  
119 x 119 | 3x3 = 117 x 117  
117 x 117 | 3x3 = 115 x 115  
115 x 115 | 3x3 = 113 x 113  
113 x 113 | 3x3 = 111 x 111  
111 x 111 | 3x3 = 109 x 109  
109 x 109 | 3x3 = 107 x 107  
107 x 107 | 3x3 = 105 x 105  
105 x 105 | 3x3 = 103 x 103  
103 x 103 | 3x3 = 101 x 101  
101 x 101 | 3x3 = 99 x 99  
99 x 99   | 3x3 = 97 x 97  
97 x 97   | 3x3 = 95 x 95  
95 x 95   | 3x3 = 93 x 93  
93 x 93   | 3x3 = 91 x 91  
91 x 91   | 3x3 = 89 x 89  
89 x 89   | 3x3 = 87 x 87  
87 x 87   | 3x3 = 85 x 85  
85 x 85   | 3x3 = 83 x 83  
83 x 83   | 3x3 = 81 x 81  
81 x 81   | 3x3 = 79 x 79  
79 x 79   | 3x3 = 77 x 77  
77 x 77   | 3x3 = 75 x 75  
75 x 75   | 3x3 = 73 x 73  
73 x 73   | 3x3 = 71 x 71  
71 x 71   | 3x3 = 69 x 69  
69 x 69   | 3x3 = 67 x 67  
67 x 67   | 3x3 = 65 x 65  
65 x 65   | 3x3 = 63 x 63  
63 x 63   | 3x3 = 61 x 61  
61 x 61   | 3x3 = 59 x 59  
59 x 59   | 3x3 = 57 x 57  
57 x 57   | 3x3 = 55 x 55  
55 x 55   | 3x3 = 53 x 53  
53 x 53   | 3x3 = 51 x 51  
51 x 51   | 3x3 = 49 x 49  
49 x 49   | 3x3 = 47 x 47  
47 x 47   | 3x3 = 45 x 45  
45 x 45   | 3x3 = 43 x 43  
43 x 43   | 3x3 = 41 x 41   
41 x 41   | 3x3 = 39 x 39  
39 x 39   | 3x3 = 37 x 37  
37 x 37   | 3x3 = 35 x 35  
35 x 35   | 3x3 = 33 x 33  
33 x 33   | 3x3 = 31 x 31  
31 x 31   | 3x3 = 29 x 29  
29 x 29   | 3x3 = 27 x 27  
27 x 27   | 3x3 = 25 x 25  
25 x 25   | 3x3 = 23 x 23  
23 x 23   | 3x3 = 21 x 21  
21 x 21   | 3x3 = 19 x 19  
19 x 19   | 3x3 = 17 x 17  
17 x 17   | 3x3 = 15 x 15  
15 x 15   | 3x3 = 13 x 13  
13 x 13   | 3x3 = 11 x 11  
11 x 11   | 3x3 = 09 x 09  
09 x 09   | 3x3 = 07 x 07  
07 x 07   | 3x3 = 05 x 05  
05 x 05   | 3x3 = 03 x 03  
03 x 03   | 3x3 = 01 x 01   
