# Matrix-Multiplication-Using-CUDA
Implemented a matrix multiplication algorithm using CUDA, with specific constraints regarding matrix dimensions and values.

You are given N matrices, where each matrix is associated with the following properties:
• r: the number of rows.
• c: the number of columns.
• v: the value of the matrix.

Your task is to:
1. Sort these matrices based on their r values in ascending order. If 2 matrices have
the same r values, sort on the c values. If the c values are same too, maintain the
original order between them.

2. In this sorted list, multiply matrix Oi ×Oi+1, lowest value first, meaning that v(Oi) is the smallest value of all matrices. The resultant matrix assumes the value and position of Oi+1 in the list. Continue multiplications until no further multiplications are possible. (If Oi is the the last matrix in the list, do not multiply.)

Note that there may be multiple matrices, including consecutive matrices, with the same value at some step. In that case, multiple multiplications are to proceed in parallel. However, if v(Oi) = v(Oi+1), Oi wins this round: multiply Oi ×Oi+1, unless Oi is dormant because v(Oi−1) = v(Oi) and Oi−1 beats Oi. Thus, every other matrix wins in a sequence of them with equal values.

For example, if the matrix order after sorting is A,B,C,D,E,F, and the values are,
respectively, 1,1,1,2,1,2, then we multiply A×B -> B, C×D -> D, E×F -> F at the
first step (all winning values 1). Matrix B also had a value 1, but since A beats it,
B×C cannot proceed.
