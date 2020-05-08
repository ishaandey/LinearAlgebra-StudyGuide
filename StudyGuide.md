# Linear Algebra Notes 

### Ishaan Dey | Spring 2020
##### MATH 3350 | Holt Linear Algebra 2nd Ed.

$$
\renewcommand{\vec}[1]{\mathbf{#1}}
$$

## Ch 1

### 1.2 Intro stuff

<u>Thm</u>: Any system of linear eqs has either 0, exactly 1, or $\infty$ many solutions

<u>How to</u>: check how many solutions there are in a given system of eq:
	If there last line is $0=c$, then there is $no\ solution$
	If not, are there free variables? If so, there are $inf\ many\ solutions$, otherwise $1\ solution$.

<u>Thm:</u> Homogenous systems ALWAYS are consistent, aka they have either 1 or inf many solutions.
This is b/c the trivial solution will always exist when $A\vec{x} = 0$

## Ch 2

### 2.1 Linear Combinations

<u>How to:</u> find all vectors $\begin{pmatrix}a\\b\end{pmatrix}$ s.t. $c_1u_1+c_2u_2=$$\begin{pmatrix}a\\b\end{pmatrix}$ ?
\> Augment the vector with $\begin{pmatrix}a\\b\end{pmatrix}$ and row reduce, the remaining things in the augment become the scalars $c_1 , c_2$ 

<u>How to</u>: show that a certain vector $\vec{b}$ cannot be obtained as a linear combination of some other vectors?
\> Augment the matrix with b then row reduce, you'll find an inconsistent set with $0=c$

### 2.2 Span

<u>Definition</u> of $span\{\vec{u_1...u_m}\} $ is the set of ALL linear combinations 

<u>How to</u>: See if some vector $\vec{v}$ is an element of $span\{\vec{u_1...u_m}\} $?
\> iff the linear system w/  $\vec{v}$ as the augment has a solution

<u>Thm</u>: IF $\vec{u, v}$ are in $span\{\vec{u_1...u_m}\}$, THEN   $\vec{u+v}$  &  $a\vec{u}$  are in that span 
(linear combinations of the vectors are in that span)

<u>How to:</u> Find a vector $\vec{b}$ not in a given span of vectors?
\> Set matrix equal (by augment) to some $(a, b, c)$, and track what happens to it until matrix is row reduced.
\> If the row is $[ 0\ 0\ 0 | f(c) ]$, then any vector that has $f(c) \neq 0$ is not in the span

<u>Thm:</u> ($span\{u_1...u_m\} = \mathbb{R} ^n$) $\iff$ ($B$ has a <u>pivot</u> in every <u>row</u>)

<u>How to:</u> check if a set of vectors span $\mathbb{R}^n$?
\> Row reduce the matrix augmented with $[a\ b\ c]$
	\> Check if there is a row of 0s, which would imply that there could be a vector not in that span 
	\> If there is a pivot in every row, there are either 1 or inf many ways to get to any point in $\mathbb{R} ^n$ (depending on if there are free variables in any of the columns)

<u>How to</u>: Find what values of $h$ in a $n$ x $m$ matrix allow it to span $\mathbb{R} ^n$ ?
	a. Row reduce the matrix, moving the $h$ down as needed to the last row.
	b. The vectors in $ A$ span $\mathbb{R} ^n$ $\iff$ there is a trivial solution, which only occurs when $f(h) \neq 0$
	c. The final answer should be all vectors with $\{h|h\neq27\}$ or something

<u>How to:</u> find $span(\vec{\{a_1...a_m}\})$ (aka the columns of T)?

<u>Thm:</u> For a given set of *m* vectors in  $\vec{R}^n$:
	a. IF $m < n$, THEN  the set does <u>not</u> span $\vec{R}^n$ (b/c theres no way to have a pivot in every row)
	b. IF $m\geq n$, THEN the set could span $\vec{R}^n$ (depends on whether or not they are linearly independent)

<u>Thm</u>:   $\vec{b}\ \epsilon\ span\{\vec{a_1...a_m}\}\ \text{in}\ \mathbb{R}^n$ $\iff$$A\vec{x}\ = \vec{b} $ has at least 1 solution

### 2.3 Linear Independence

<u>Definition</u>: IF the only way to express $\vec{0}$ as a linear combination of $\vec{A}$ is the trivial solution $\vec{0}$, THEN the system is *linearly independent*. Nontrivial solutions imply *linear dependence*.
<u>Thm</u>:   ($\vec{Ax=0}$ has only the trivial solution) $\iff$ ( $\{\vec{a_1...a_m}\}$ is linearly independent )

<u>How to:</u> Check if a system is linearly independent?
	a. Set the sytem equal to $\vec{0}$, and row reduce. The only solution should be $\vec{x} = \vec{0}$ (which will happen when there is a pivot in every column)

<u>Thm:</u>  ($m$ vectors in  $\mathbb{R}^n$ are linearly independent) $\implies$ ($m\leq n$)
	(b/c you can't have pivots in every column if there are too many columns)
	(in other words, there are more variables than equations in the system)

<u>Thm:</u> For a given set of $m$ vectors in  $\mathbb{R}^n$:
	a.   ( $span\{u_1...u_m\} = \mathbb{R}^n$ ) $\iff$ ($B$ has a pivot in every <u>row</u>)
	b.  ( $\{u_1...u_m\}$ are linearly independent ) $\iff$ ($B$ has a pivot in every <u>column</u>)

<u>How to:</u> Check if one vector lies in the span of others in a set?
	a. Row reduce the matrix augmented with $\vec{0}$
	b. If B does not have a pivot in every column $\implies$ the system is linearly dependent $\implies$ one of the vectors lies in the span of the others

###### General vs. Particular Solutions to Ax=0

<u>Thm</u>: $\vec{x_g = x_p + x_h}$, where $\vec{x_g}$ is the solution to $\vec{Ax=b}$, $\vec{x_h}$ is the solution to the associated homogenous system $\vec{Ax=0}$, and $\vec{x_p}$ is a particular solution to $\vec{x_g}$

<u>Thm:</u> For a given set of vectors $\{\vec{a_1...a_m}\}$ and $\vec{b}$ in  $\mathbb{R}^n$:
	a.  ( $\{\vec{a_1...a_m}\}$ are linearly independent) $\iff$ ($\vec{Ax=b} $)

## Ch 3

### 3.1 Linear Transformations

<u>Definition</u>: A transformation $T\vec{(x)=Ax}$ is <u>linear</u> if both:
	a. $T\vec{(u+v)=A(u+v)\ \ =\ \ A(u)+A(v)=T(u)+T(v)}$
	b. $T\vec{(}r\vec{u)=A(}r\vec{u)\ \ =}$  $r\vec{A(u)}=rT(\vec{u})$

<u>Thm</u>: $T\vec{(x)=Ax}$ $\implies$ $T$ is a linear transformation, where $A$ is a $n x m$ matrix, and $T$ goes from $\vec{R^m}$ to $\vec{R^n}$ 

<u>How to</u>: Check if a given transformation is linear:
	a. Convert the system into a matrix A
	b. Plug in the vectors $\begin{pmatrix}x_1\\x_2\end{pmatrix}$ for $\vec{u}$ and $\begin{pmatrix}y_1\\y_2\end{pmatrix}$ for $\vec{v}$ to prove the general case *true*
	c. Try the basis vectors $\begin{pmatrix}1\\0\end{pmatrix}$ and $\begin{pmatrix}0\\1\end{pmatrix}$ independently and check if the output fails to prove *false*

<u>How to</u>: Find $range(T)$, where $\vec{T(x)=Ax}$  :
	a. $range(T) = span(\{\vec{a_1...a_m}\})$ 
	b. range is the set of linear combinations of the columns of $A$

<u>How to:</u> Check if a given vector $\vec{w}$ is in $range(\vec{T})$:
	a. Make matrix of $\vec{[A\ |w]}$ and solve

###### One-to-One vs Onto

<u>Definition</u>: A transformation is *one-to-one* when there's at most one input that maps to an output
<u>Definition</u>: A transformation is *onto* when no element in the codomain $B$ is left out

<u>Thm</u>: Given $T: \mathbb{R} ^m \rightarrow \mathbb{R} ^n$ and  $T\vec{(x)=Ax}$, where $B$ is $A$ in row-echelon form:
	1a. ($T$ is one-to-one) $\iff$ (columns of $A$ are linearly *in*dependent) $\iff$ ($B$ has a pivot in every column)
	1b. $n < m \implies$ T is not one-to-one (aka if output space is smaller than input space)

​	2a. ($T$ is onto) $\iff$ (columns of $A$ span the codomain $\mathbb{R}^n$ aka $range(T)=\mathbb{R}^n$) $\iff$ ($B$ has a pivot in every row)
​	2b. $n > m \implies$ T is not onto (aka if output space is bigger than input space)

​	\> "No matrix that goes from bigger space to smaller space can be one-to-one"
​	\> "No matrix that goes from small space to bigger space can be onto"

###### Geometry of transformations

<u>How to</u>: Rotate a vector CCW by $\theta$ :
	a. $T_r(\vec{x}) = \begin{pmatrix}cos(\theta)&-sin(\theta)\\sin(\theta)&cos(\theta)\end{pmatrix} \vec{x}$

<u>How to</u>: Shear to the right:
	a.  $T_r(\vec{x}) = \begin{pmatrix}1&1\\0&1\end{pmatrix} \vec{x}$

<u>How to:</u> Find the transformation for a parallelogram from a unit square:
	a. $\vec{a_1}$ , or the first column of $A$ defines where the first basis vector, $\vec{i}$, lands;  same for $\vec{a_2}$

### 3.2 Matrix Algebra

###### Properties of Elementary Matrices

a. $A(BC)=(AB)C$
b. $A(B+C) = AB+AC$
c. $(A+B)C = AC+BC$
d. $s(AB) = (sA)B = A(sB)$
e. $AI = IA = A$

###### Non-Properties of Nonzero Matrices 

a. It is possible that $AB \neq BA$ (Unless both are square)
b. $AB=0$ does not imply that $A=0$ or $B=0$
c. $AC = BC$ does not imply that $A=B$ or $C=0$ (unless $A$ is invertible)

###### Transpose of a Matrix 

a. $(A+B)^T = A^T + B^T$
b. $(sA)^T = sA^T$
c. $(AC)^T = C^T A^T$

##### 3.3 Inverses

<u>Definition</u>: If T is a linear transformation, Then
	a. $T$ has an inverse $\implies$  $m=n$ 
	b. If $T$ is invertible, then $T^{-1}$ is also a linear transformation

($T$ is invertible) $\iff$ ($T$ is one-to-one AND onto)

<u>How to:</u> find an invertible matrix $A^{-1}$?
	a. Augment matrix A with $I_n$ , then row reduce until you get  $I_n$ augmented with $A^{-1}$ 
	(aka $[A|I_n]\rightarrow[I_n|A^{-1}]$ )

<u>Thm:</u> Elementary matrices are invertible

###### Properties of Inverses

​	a. $(A^{-1})^{-1} = A$ 
​	b. $(AB)^{-1} = B^{-1}A^{-1}$ 
​	c. $AC=AD \implies C=D$
​	d. $AC=0_{nm} \implies C=0_{nm}$

## Ch 4

### 4.1 Subspaces

<u>Definition</u>: A subset of S is a subspace if all three conditions are true:
	a. S contains $\vec{0}$   (S contains the origin)
	b. If $\vec{u}$ and $\vec{v}$ are both in S, then $\vec{(u+v)}$ is in S (S is closed under addition)
	c. If $r\ \epsilon\ \mathbb{R}$ , then $r\vec{u}$ is also in S (S is closed under scalar multiplication)

<u>Thm</u>: If S = $span\{\vec{u_1...u_m}\}$ in $\mathbb{R}^n$, then S is a subspace of $\mathbb{R}^n$

<u>How to:</u> Check if S is a subspace?
	a. Check if $\vec{0}$ is in S, which it must be to be a subspace
	b. Try to show S is generated by a set of vectors (See if it can be composed as a matrix of coefficients)

<u>Definition</u>: If $\vec{A}$ is a $n$ *x* $m$ matrix, then the set of solutions to $\vec{Ax=0}$ is called $null(\vec{A})$ 
	(aka the null space is all linear combinations where $\vec{Ax=0}$)
	(aka the null space is the solution to the homogenous system)

<u>Thm</u>: If $\vec{A}$ is a $n$ *x* $m$ matrix, then the set of solutions to $\vec{Ax=0}$ forms a subspace of $\mathbb{R}^m$ 
	(aka null space is a subspace)

<u>Thm</u>: Given $T:\ \mathbb{R}^m\ \rightarrow\ \mathbb{R}^n$ is a *linear* transformation:
	a. $ker({T})$ is a subspace of the domain $\mathbb{R}^m$
	b. $range({T})$ is a subspace of the *co*domain $\mathbb{R}^n$ 

\> "The kernel is the set of vectors that are sent to {$\vec{0}$} after applying $T$"
\> "The range of T is the span after applying $T$"

<u>How to</u>: Find $ker(T)$ of $T(\vec{x}) = A(\vec{x})$?
	a. $(T\vec{(x)=Ax}) \implies$ ( $ker(T) = null(A)$ ), so solve for $\vec{Ax=0}$, and $ker(T)$ is the span of that answer
<u>How to</u>: Find $range(T)$ of $T(\vec{x}) = A(\vec{x})$?
	a. $range(T) = span(\vec{a_1...a_m})$, so just delete any linearly *dependent* columns of $\vec{A}$ and that's your answer

<u>Thm</u>: (T is one-to-one) $\iff$ ( $ker(T) = \{\vec{0}\}$ )       

### 4.2 Basis vectors

<u>Definition</u>: Set $\mathcal{B}$ $= \vec{\{u_1...u_m\}}$ is a *basis* of subspace S iff:
	a. $\mathcal{B}$ spans S
	b. $\mathcal{B}$ is linearly independent
"To get to any point in $S$, you can take a linear combination of the basis vectors to get there"

<u>How to</u>: find a basis for $S$ = span$\vec{\{u_1...u_m\}}$? 
*Method 1 (Thm 4.10):*
	a. Create a matrix $\begin{pmatrix}\vec{u_1\\...\\u_m}\end{pmatrix} $
	b. Row reduce to $B$
	c. The nonzero *rows* of $B$ give a basis of $S$
*Method 2 (Thm 4.11):*
	a. Create a matrix out of $\vec{\{u_1...u_m\}}$
	b. Row reduce to $B$. The pivot columns of $B$ are linearly independent 
		(the other cols  are dependent on the pivot columns)
	c. The *columns of $A$* corresponding to the *pivot columns of $B$* form a basis of S. 

###### Dimension

<u>Thm</u>: If $S$ is a subspace of $\mathbb{R} ^n$, then every basis of $S$ has the same number of vectors

<u>Definition</u>: If $S$ is a subspace of $\mathbb{R} ^n$, then the *dimension* of $S$is the number of vectors in any basis of $S$

<u>Thm</u>: $\mathcal{U}$ = $\vec{\{u_1...u_m\}}$ is a set of $m$ vectors in subspace S of dimension $m$. 
		IF $\mathcal{U}$ is *either* linearly independent or spans S, THEN $\mathcal{U}$ is a basis for S.

<u>How to</u>: expand a set of vectors to become a basis of $\R^n$:
	a. Append on all the unit vectors of $\R$ ,  $\vec{e_i}$  ,  that you have and then row reduce down to B. 
	b. The original columns of A that correspond w/ the pivots of B become the basis vectors for $\R^n$

<u>Unifying Theorem</u>: Given *S* = $\vec\{{a_1 ... a_m}\}, \vec\{{a_1 ... a_m}\} \epsilon \mathbb{R} ^n, A =[\vec{a_1 ... a_m}]$, and $T: \mathbb{R} ^m \rightarrow \mathbb{R} ^n, T(\vec{x}) = A\vec{x}$:
	a. *S* spans $\mathbb{R}^n$
	b. S is linearly independent
	c. $A\vec{x} = \vec{b}$ has precisely 1 unique solution $\forall\ b\ \epsilon\ \mathbb{R}^n$ 
	d. $T$ is onto
	e. $T$ is one-to-one
	f. $A$ is invertible
	g. $ker\{T\}=\{\vec{0}\} \iff null(A)=\{\vec{0}\}$
	h. *S* is a basis of $\mathbb{R}^n$ 

### 4.3 Row and Column Spaces

<u>Definition</u>: Row vectors of $A$ come from viewing $A$ as a set of rows; Column vectors of $A$ come from viewing $A$ as a set of columns.

<u>Definition</u>: Given $A$ is a $n$ x $m$ matrix:
	a. $row(A)$ or row space is the subspace of $\mathbb{R^m}$ spanned by *row vectors* of $A$
	b. $col(A)$ or column space is the subspace of $\mathbb{R^n}$ spanned by *column* vectors of $A$

<u>Thm</u>: Given matrix $A$ and $B$ in echelon form:
	a. Nonzero rows of $B$ form a basis for $row(A)$
	(The redundant rows get killed off by row reduction)
	b. The cols of $A$ corresponding to pivot columns of $B$ form a basis for $col(A)$
	(The pivot columns are linearly independent  $\implies$  they form the column space of A)

<u>Thm</u>: For any matrix A, the dimension of $row(A)$ equals the dimension of $col(A)$
(aka the number of basis vectors needed to define $row(A)$ the number needed to define $col(A)$)

<u>Definition</u>: $rank(A)$ is the dimension of $row(A)$ or $col(A)$

<u>Rank-Nullity Thm</u>: IF $A$ is a $n$ x $m$ matrix, THEN $rank(A) + nullity(A) = m$ (# of cols)
( $nullity(A)$ is the number of free variables in the system $A\vec{x}=0$ )
*Note: $ker(T) $ is $ null(A), $ and $ range(T)$ is $col(A)$

<u>Thm</u>: IF $A$ is a $n$ x $m$ matrix, and $\vec{b}$ is a vector in $\mathbb{R^n}$:
	a. The system $A\vec{x}=\vec{b}$ is consistent (one or many solutions) $\iff$ $\vec{b}$ is in $col(A)$
	b. The system $A\vec{x}=\vec{b}$ has a unique solution (exactly 1 solution) $\iff$ $\vec{b}$ is in $col(A) $ *and* columns of A are linearly independent

<u>Unifying Theorem</u>: Given *S* = $\vec\{{a_1 ... a_m}\}, \vec\{{a_1 ... a_m}\} \epsilon \mathbb{R} ^n, A =[\vec{a_1 ... a_m}]$, and $T: \mathbb{R} ^m \rightarrow \mathbb{R} ^n, T(\vec{x}) = A\vec{x}$:
	a. *S* spans $\mathbb{R}^n$
	b. S is linearly independent
	c. $A\vec{x} = \vec{b}$ has precisely 1 unique solution $\forall\ b\ \epsilon\ \mathbb{R}^n$ 
	d. $T$ is onto
	e. $T$ is one-to-one
	f. $A$ is invertible
	g. $ker\{T\}=\{\vec{0}\} \iff null(A)=\{\vec{0}\}$
	h. *S* is a basis of $\mathbb{R}^n$ 
	i. $col(A)$ = $\mathbb{R^n}$
	j. $col(A)$ = $\mathbb{R^n}$
	k. $rank(A) = n$

### 4.4 Change of Basis

<u>Definition</u>: Suppose that $B$  = $\{\vec{u_1 ... u_n}\}$ forms a basis of $\mathbb{R^n}$, and if $\vec{y}=y_1\vec{u_1}+...+y_n\vec{u_n}$:
				Then the *coordinate vector* of $y$ w.r.t. *B* is $[\vec{y}]_B = \begin{pmatrix}y_1\\...\\y_n\end{pmatrix}$
	"the coordinate vector contains the coeffs required to express y as a linear combination of vectors in basis B"

​	$	U\begin{pmatrix}y_1\\...\\y_n\end{pmatrix} = y_1\vec{u_1}+...+y_n\vec{u_n}$
​	
​	$\vec{y}=U[\vec{y}]_B$ ; where $U$ is the *change of basis matrix* that transforms the coordinate vector wrt $B$ back to the standard basis
​	($U$ is just the $n$ x $n$ matrix containing the basis vectors of set B: $[\vec{u_1 ... u_n}]$ )

<u>Thm</u>: Let $\vec{x}$ be expressed wrt standard basis, and *B*  = $\{\vec{u_1 ... u_n}\}$ be any basis for $\mathbb{R^n}$:
	If $U$ = $[\vec{u_1 ... u_n}]$, then: $\vec{x}=U[\vec{x}]_B$ and $[\vec{x}]_B = U^{-1}\vec{x}$ 
	"$U$ takes us from a vector described with a weird basis into our standard definition"
	"$U^{-1}$ tells us how to define a vector w/ standard definition into back into weird basis land"

<u>How to:</u> Move from one nonstandard basis to another?
If $B_1$ = $\{\vec{u_1 ... u_n}\}$ corresponds to U and $B_2$ = $\{\vec{v_1 ... v_n}\}$ corresponds to V, then:
	$[\vec{x}]_{B_2} = V^{-1}U[\vec{x}]_{B_1}$
	$[\vec{x}]_{B_1} = U^{-1}V[\vec{x}]_{B_2}$

​	"To go from basis 1 to basis 2, apply $U$ to go from basis 1 land into standard basis, then apply  $V^{-1}$ to go to basis 2 land"

INSERT PIC

## Ch 5

### 5.1 Determinant

<u>Definition:</u> Given A is a $nxn$ matrix, each position is defined as $a_{ij}$:
	a. cofactor  $C_{ij} = (-1)^{i+j}*det(M_{ij})$, where $M_{ij}$  is the rest of the matrix that doesn't include the $i$th row & $j$th column ($M_{ij}$ is called the Minor of $i,j$)
	b. $det(A)=a_{11}C_{ij}+...+a_{1n}C_{1n}$ :  for each element in the *first* column, multiply each times its cofactor. 
	c. In general, you can expand down <u>any</u> row or column and apply the same formula (<u>Thm 5.8</u>)

<u>Matrix of signs of cofactors</u>: $ \begin{pmatrix} +  -  +  - \\ -  +  -  + \\  +  -  +  - \\  -  +  -  + \\ \end{pmatrix}; \text{where } C_{ij}=(-1)^{i+j}$

<u>Thm 5.5:</u> $det(I_n)=1$

<u>Thm 5.6:</u> $A$ is invertible $\iff$ $det(A) \neq 0$ 
	\> This would invoke unifying theorem, so you could say things like: "cols of A form a basis of $\R^{n}$ " etc.

<u>Thm 5.9</u>: If $A$ is triangular matrix, then $det(A)$ is product of terms along the diagonal

<u>Thm 5.11:</u> If $A$ is a square matrix, then:
	a. If $A$ has a row or column of zeros, then $det(A)=0$
	b. If $A$ has two identical rows or columns, then $det(A)=0$

### 5.2 Properties of Determiniants

<u>Thm 5.13</u>: 
	a. Swap 2 rows of A $\implies$ $-det(A)$
	b. Multiply row of A by $c$ $\implies$ $c*det(A)$
	c. Add multiple of one row of A to another $\implies$ $det(A)$

<u>Thm 5.10:</u> If $A$ is a square matrix, then $det(A^T) = det(A)$

If $ A $ is invertible, $det(A^{-1}) = \frac{1}{det(A)}$

<u>Thm 5.12:</u> $\det(AB)=det(A)det(B)$ if $A$ and $B$ are both $n$ x $n$ matrices

### 5.3 Applications of Determinants

<u>Cramer's Rule (Thm 5.17):</u> Let $A$ be invertible; to find unique solution, $\vec{x}$, to $A\vec{x}=\vec{b}$:
	 $\vec{x}_i=\frac{det(A_i)}{det(A)}$, where $A_i$ is the matrix $A$ but with the $i$th column replaced by $\vec{b}$

<u>How To:</u> Find the unique solution to $A\vec{x} = \vec{b} $ :
	\> Apply Cramer's Rule for each column in $A$

<u>Thm 5.18:</u> If $A$ is invertible, then:
	$A^{-1}=\frac{adj(A)}{det(A)}$, where $\text{adj}(A)=C^T$, the transpose of the cofactor matrix of $A$

<u>Thm</u>: $A(\text{adj}(A))=\det(A)*I_n$

<u>Thm 5.20:</u> Let *D* be a region w finite area in $\vec{R}^2$, $T(\vec{x})=A\vec{x}$, and $T(D)$ is the image of *D* under $T$, then:
	$\text{area}(T(D)) = |\text{det}(A)|*\text{area}(D)$

<u>Thm 5.21:</u> Same thing as Thm 5.20 but w/ $\text{volume}$ in $\vec{R}^3$ 

## Ch 6

### 6.1 Eigenvalues and Eigenvectors

<u>Definition:</u> Let $A$ be a $n$ x $n$ matrix; $\vec{u}$ is an eigen*vector* of $A$ if there exists a scalar $\lambda$ s.t. 
			$A\vec{u}=\lambda\vec{u}$ ; where $\lambda$ is an eigen*value* of $A$
		<u>Intuition</u>: If $A$ is a transofrmation that changes the basis vectors of our subspace, 
		then we expect most vectors to also be transformed in some manner (sheared, etc).
		Eigen*vectors* are the specific vectors that remain parallel after the transformation, 
		and the degree to which its scaled is called the eigen*value*

<u>Thm 6.2:</u> If $\vec{u}$ is an eigenvector of $A$ associated with $\lambda $, then $c\vec{u}$ is also associated w/ $\lambda$

<u>How to:</u> Check if a given vector $\vec{u}$ is a eigenvector of $A$?
		a. Multiply $A*\vec{u}$, and the result should be some multiple $ c \vec{u} $

<u>How to:</u> Find an eigenvector if you know the eigenvalues for a given $n$x$n$ matrix $A$:
	For a specific eigenvector, say  $\lambda =6$:  $(A\vec{u}-6I_{n})\vec{u}=\vec{0}$
		a. Subtract off $6$ from each value along the *diagonal* of $A$
		b. Then set equal to $\vec{0}$ and solve out
		c. You'll get something like $s_1 \begin{bmatrix}-2\\-1\\0\end{bmatrix} + s_2 \begin{bmatrix}1\\0\\1\end{bmatrix}$, which means any vector $\vec{u}$ that is a linear combination of the
			those two is an eigenvector (this is called the eigenspace btw)

<u>Thm 6.3:</u> If $A$ is a $n$x$n$ matrix w/ eigenvalue $\lambda$, and $S$ is the set of all eigenvectors associated w/ $\lambda$, including $\vec{0}$ :
		Then $S$ is a subspace of $\vec{R}^n$

<u>Definition:</u> Eigenspace of $A$ is the subspace of all eigenvectors associated w/ $\lambda$  together w/ $\vec{0}$

<u>Thm 6.5:</u>  $\lambda$ is an eigenvalue of $A$ $\iff$ $det(A-\lambda I_n)=0$

<u>How to:</u> find eigenvalues of $A$:
		a. Subtract off $\lambda $ from each diagonal, and take the determinant of that matrix
					The result is called the characteristic polynomial btw
		b. Set that equal to 0, and solve for lambda

<u>Definition:</u> Multiplicity is the number of times a root of the characteristic equation is repeated, aka multiplicity is equal to its factor's exponent

<u>Thm 6.6:</u> Let $A$ be a square matrix w/ eigenvalue $\lambda$: Then $\text{dim}$ of associated eigenspace is $\leq$ multiplicity of $\lambda$

<u>Thm 6.7</u>: Unifying thm: $\lambda=0$ is not an eigenvalue of $A$
		In other words, if $\lambda$ $=0$ *is* an eigenvalue of $A$, then one of the columns is linearly dependent or something

### 6.2 Diagonalization

<u>Definition</u>: $A$ is diagonalizable if there exists $n$x$n$ matrices $D$ and $P$, s.t. $D$ is diagonal and $P$ is invertible:
						=>	$A=PDP^{-1}$

<u>How to:</u> Find $P$ and $D$ to diagonalize matrix $A$:
		a. Find each eigenvalue using $det(A-\lambda I_n)=0$
		b. Find the associateed eigenvector by solving the homogenous system $(A-I_n)\vec{u}=\vec{0}$
		c. $P=[\vec{u}_1, \vec{u}_2 , ..., \vec{u}_n]$ ;  $D = \begin{bmatrix} \lambda_1\ & 0 \\ 0 & \lambda_2 \end{bmatrix} $ 

<u>Thm</u>: 
		$det(A)=det(PDP^{-1})=det(D)=$ product of $\lambda_i$s
        If $A$ is triangular, eigenvalues lie along the diagonal

<u>Thm 6.9:</u> $A$ is diagonalizable $\iff$ $A$ has eigenvectors that form a basis for $\vec{R}^n$ 
		$\iff$ $A$ has $n$ linearly *independent* eigenvectors

<u>Thm 6.10:</u> If $\{ \lambda_1,...,\lambda_k \} $ are distinct eigenvalues of $A$, 
				 then any set of associated eigenvectors $\{ \vec{u_1},...,\vec{u}_k \}$ are *linearly independent* 
		\> Means that vectors from *distinct* eigenspaces are linearly independent
​		\> This also means that $A$ can be not invertible and yet diagonalizable

<u>Thm 6.11:</u> If $A$ has only real eigenvalues, then:
			$A$ is diagonalizable $\iff$ $\text{dim}$ of each eigenspace *equals* the multiplicity of corresponding eigenvalue
		\> Means that you'll know that a matrix isn't diagonalizable (for example) when you see that there's one basis vector of an eigenspace when the root had a power of 2

<u>Thm 6.12:</u> If $A$ is a $n$ x $n$ matrix with $n$ *distinct* real eigenvalues, then $A$ is diagonalizable

<u>How to</u>: Get $k$th power of matrix:   $A^k=PD^{k}P^{-1}$

## Ch 7

### 7.1 Vector Spaces + Subspaces

<u>Definition</u>: Vector space is a set $V$ of vectors, together w/  operations of addition and scalar multiplication:
		a. $V$ is closed under addition: 	If $\vec{v}_1$ and $\vec{v}_2$ are in $V$, then so is $\vec{v}_1+\vec{v}_2$
		b. $V$ is closed under *scalar* multiplication: 	If $c$ is a real scalar and $\vec{v}$ is in $V$, then so is $c\vec{v}$
		c. There exists a zero vector $\vec{0}$ in $V$ s.t. $\vec{0}+\vec{v}=\vec{v}$ for all $\vec{v}$ in $V$
		d. There exists an additive inverse $-\vec{v}$ in $V$ s.t. $\vec{-v}+\vec{v}=\vec{0}$ for all $\vec{v}$ in $V$
		e. For all $\vec{v}_1, \vec{v}_2, \vec{v}_3$ in $V$:
				a. $\vec{v}_1 + \vec{v}_2 = \vec{v}_2 + \vec{v}_1$
				b. $(\vec{v}_1 + \vec{v}_2) + \vec{v}_3 = \vec{v}_1 + (\vec{v}_2 + \vec{v}_3) $
				c. $c_1(\vec{v}_1+\vec{v}_2) = c_1\vec{v}_1+c_1\vec{v}_2$
				d. $(c_1 + c_2)\vec{v}_1 = c_1\vec{v}_1 + c_2\vec{v}_1$
				e. $(c_1c_2)\vec{v}_1 = c_1(c_2\vec{v}_1)$
				f. $1*\vec{v}_1 = \vec{v}_1$

<u>Thm 7.2:</u> Let $\vec{v}$ be in vector space $V$:
		a. $\vec{0}$ is the zero vector in $V$ $\implies$ $\vec{v}+\vec{0}=\vec{v}$
		b. $-\vec{v}$ is the additive inverse of $\vec{v}$ $\implies$ $-\vec{v}+\vec{v}=\vec{0}$
		c. $\vec{v}$ has a unique additive inverse $-\vec{v}$
		d. Zero vector $\vec{0}$ is unique
        e. $0*\vec{v}=\vec{0}$
		f. $(-1)*\vec{v}=-\vec{v}$

<u>Definition</u>: A subset $S$ of a vector space $V$ is a subspace if $S$:
		a. $S$ contains the zero vector, $\vec{0}$
		b. If $\vec{u}, \vec{v}$ is in $S$, then $\vec{u}+\vec{v}$ is also in $S$
		c. If $c$ is a scalar and $\vec{v}$ is in $S$, then $c\vec{v}$ is also in $S$

### 7.2 Span and Linear Independence

<u>Definition:</u> Span of set $\{ \vec{v}_1, \vec{v}_2, ..., \vec{v}_m \}$ is set of all linear combinations of the form: $c_1\vec{v}_1+c_2\vec{v}_2+...+c_m\vec{v}_m$

<u>Thm 7.6:</u> Suppose that $\mathcal{V}$ is a subset of vector space $V$, and let $S = \text{span}(\vec{\mathcal{V}})$ then $S$ is a subspace of $\mathcal{V}$

<u>Definition:</u> Set $\mathcal{V}$ = $\{ \vec{v}_1, \vec{v}_2, ..., \vec{v}_m \}$ is linearly *in*dependent if $c_1\vec{v}_1+c_2\vec{v}_2+...+c_m\vec{v}_m = \vec{0}$ has only the trivial solution

<u>Thm 7.8</u> Set $\mathcal{V}$ = $\{ \vec{v}_1, \vec{v}_2, ..., \vec{v}_m \}$ is linearly *de*pendent $\iff$ at least one vector is in the span of the others

<u>Thm 7.9</u> If set $\mathcal{V}$ = $\{ \vec{v}_1, \vec{v}_2, ..., \vec{v}_m \}$ is a subset of $V$, then:
		a. $\mathcal{V}$ is *linearly independent* $\iff$ $\{ \vec{v}_1, \vec{v}_2, ..., \vec{v}_m \}=\vec{v}$ has *at most* one solution for each $\vec{v}$ in $V$
        b. $\mathcal{V}$ *spans* $V$ $\iff$ $\{ \vec{v}_1, \vec{v}_2, ..., \vec{v}_m \}=\vec{v}$ has *at least* one solution for each $\vec{v}$ in $V$

<u>How to:</u> Check if a system is linearly independent, i.e. given $a(1)+b(sin(x))+c(cos(x))=0$?
		a. To generate a system of equations, take the first and second derivatives wrt. $x$ to generate 3 equations
		b. Check if the determinant $\neq 0$, $\implies$ the matrix is invertible, $\implies$ the system $A\vec{x}=\vec{0}$ has a unique solution which is the trivial solution.

<u>Application:</u> Decomposition of signal frequencies:
		I.e. Given $1, sin(x), cos(x), sin(2x), cos(2x),..., sin(nx), cos(nx)$, is this system linearly independent?

<u>Definition:</u> $\mathbb{P}^n$ is the set of all polynomials of degree $\leq n$
		a. Standard bases: $\{1,x,x^2,...,x^n\} \implies dim(\mathbb{P}^n)=n+1$
		b. $\text{dim } \mathbb{P} = \infin$, enough to show that there is no finite basis
			b1. $\mathbb{P} \subseteq C(\R) \implies \text{dim } C(\R) = \infin$

<u>How to</u>: check if a given set of polynomials, i.e. $\{x+1,x^2-1,x^2+x+1\}$, is a basis of $\mathbb{P}^2$?
		

a. Check linear independence: Assign a scalar $c_i$ to each polynomial; each column represents $c_i$, and each element in each *column* corresponds to a different degree of that polynomial, i.e. $x^2$
			$c_1(x+1)+c_2(x^2-1)+c_3(x^2+x+1)=\vec{0}$
			$\implies (c_1-c_2+c_3)*1+(c_1+c_3)*x+(c_2+c_3)*x^2=0$
			$\implies \begin{pmatrix} 1\ -1\ 1 \\ 1 \ 0 \ 1 \\ 0 \ 1 \ 1 \end{pmatrix} \begin{pmatrix}c_1\\c_2\\c_3\end{pmatrix} = \begin{pmatrix}0\\0\\0\end{pmatrix}$
			a1. Check that determinant $\neq 0$ which would imply unique trivial solution, which implies linear independence
		b. Could also check that they $\text{span } \mathbb{P}^2$
			$\implies \begin{pmatrix} 1\ -1\ 1 \\ 1 \ 0 \ 1 \\ 0 \ 1 \ 1 \end{pmatrix} \begin{pmatrix}c_1\\c_2\\c_3\end{pmatrix} = \begin{pmatrix}a\\b\\c\end{pmatrix}$
		c. Could also check matrix of derivatives: if there exists at least a single value of $x$ that makes $det(A) \neq 0$, $\implies$ linear indpendence.
			$\begin{vmatrix} x+1& x^2-1 & x^2+x+1 \\ 1 & 2x & 2x+1 \\ 0 & 2 & 2 \end{vmatrix}$

### 7.3 Basis and Dimension

<u>Definition:</u> $\mathcal{V}$ is a basis of $V$ if $\mathcal{V}$ is linearly independent *and* spans $V$

<u>Thm 7.11</u> Set $\mathcal{V}$ = $\{ \vec{v}_1, ..., \vec{v}_m \}$ is a basis of vector space $V$ iff:
		$\{ \vec{v}_1, \vec{v}_2, ..., \vec{v}_m \}=\vec{v}$ has a *unique* solution for every $\vec{v}$ in $V$	

<u>Thm 7.12</u> If $\mathcal{V_1}$ and $\mathcal{V_2}$ are both bases of vector space $V$, then $\mathcal{V_1}$ and $\mathcal{V_2}$ have the same number of elements
<u>Definition</u> Dimension of $V$ is equal to the number of vectors in any basis of $V$. *It's possible for dimension to be infinte if the basis of $V$ is infinitely long*

<u>Thm 7.14</u> Let $\mathcal{V}$ = $\{ \vec{v}_1, ..., \vec{v}_m \}$ be a subset of *nontrivial, finite, dimensional* vector space $V$:
		a. If $\mathcal{V}$ spans $V$, then either $\mathcal{V}$ is a basis of $V$ or vectors can be removed from $\mathcal{V}$ to form a basis of $V$
		b. If $\mathcal{V}$ is linearly independent, then either $\mathcal{V}$ is a basis of $V$ or vectors can be added to $\mathcal{V}$ to form a basis of $V$

<u>Thm 7.15:</u> If $V_1$ is a subspace of $V_2$, then $\text{dim}(V_1) \leq \text{dim}(V_2)$

<u>Thm 7.16:</u> Let $\mathcal{V}$ = $\{ \vec{v}_1, ..., \vec{v}_m \}$ be a subset of $V$ with $\text{dim}(V)=n$.
		a. If $m<n$, then $\mathcal{V}$ does not span $V$
		b. If $m>n$, then $\mathcal{V}$ is not linearly independent

<u>Thm 7.17:</u> Let $\mathcal{V}$ = $\{ \vec{v}_1, ..., \vec{v}_m \}$ be a subset of $V$ with $\text{dim}(V)=m$.
		a. If $\mathcal{V}$ is linearly independent *or* spans $V$, then $\mathcal{V}$ is a basis for $V$

<u>How to:</u> find $dim \text{ span}\{T_1,T_2,T_3\}$, given something like $T_1\vec{x}=\begin{pmatrix}x_1 + x_2 \\ 2x_1 \end{pmatrix}$, etc.?
		a. Check linear independence of $T_1, T_2, T_3$ (Must hold $\forall\ x$ )
			a1. Assign each $T_i$ a scalar $c_i$ which become its own columns; 
				each element in that matrix has its own row on that particular column
			b. Row reduce: if you get a free variable in a certain column, say $s_1$, then that column is a linear comination of the others
		b. Check how many $T$s are needed to maintain linear independence, that is $dim \text{span}$


## Ch 8

### 8.1 Dot Products and Orthogonal Sets

<u>Definition</u> If $\vec{u} = \begin{bmatrix} u_1\\ \vdots \\ u_n \end{bmatrix}$ and $\vec{v} = \begin{bmatrix} v_1\\ \vdots \\ v_n \end{bmatrix}$ in $\vec{R}^n$:	$\vec{u}\sdot\vec{v} = u_1v_1+\cdots+u_nv_n = \vec{u}^T\vec{v} $

<u>Thm 8.2:</u> Properties of dot products:
		a. $\vec{u}\sdot\vec{v}=\vec{v}\sdot\vec{u}$
		b. $(\vec{u}+\vec{v})\sdot\vec{w} = \vec{u}\sdot\vec{w} + \vec{v}\sdot\vec{w}$
		c. $(c\vec{u})\sdot\vec{v}=\vec{u}\sdot(c\vec{v})=c(\vec{u}\sdot\vec{v})$
		d. $\vec{u}\sdot\vec{u}\geq=0$
		e. $ \vec{u}\sdot\vec{u}=0 \iff \vec{u}=\vec{0} $ 

<u>Definition:</u> Norm or length of $ \vec{x} = ||\vec{x}|| = \sqrt{\vec{x}\sdot\vec{x}}$
		$||c\vec{x}||=|c|\ ||\vec{x}||$

<u>Definition:</u> Unit vector in direction of $\vec{x}$:
		$||\frac{\vec{x}}{||\vec{x}||}|| = 1$ 

<u>Definition:</u> The distance between $\vec{u}$ and $\vec{v}$ in $\vec{R}^n$ is $||\vec{u}-\vec{v}||$
		a. Subtract $v_!$ from $u_1$, etc., then take the magnitude of that resulting vector
		b. This is really the distance between the endpoints of the rays

<u>Definition:</u> Vectors $\vec{u}$ and $\vec{v}$ in $\vec{R}^n$ are orthogonal if $\vec{u}\sdot\vec{v}=0$

<u>Pythagorean Thm 8.6</u>:     $||\vec{u}+\vec{v}||^2=||\vec{u}||^2+||\vec{v}||^2 \iff \vec{u}\sdot\vec{v}=0$
		a. Think middle school geometry: pythagorean thm applies iff right triangle 

<u>Cauchy-Schwarz Inequality Thm 8.7:</u> 	 $|\vec{u}\sdot\vec{v}| \leq ||\vec{u}||\text{ }||\vec{v}||$
		a. Define $cos(\theta)=\frac{\vec{u}\sdot\vec{v}}{||\vec{u}||\text{ }||\vec{v}||}$

<u>Triangle Inequality Thm 8.8</u> 	$||\vec{u} + \vec{v}|| \leq ||\vec{u}||+||\vec{v}||$
		a. This says that the line segment between two vectors is the shortest way between those two points 

######  Orthogonal Subspaces

<u>Definition:</u> Vector $\vec{u}$ is orthogonal to subspace $S$ if $\vec{u}\sdot\vec{v}=0\ \forall \ \vec{s} \in S$. The set of all such vectors $ \vec{u}$ is called the orthogonal complement of $S$ and is denoted by $S^\bot$
			$S^\bot=\{\vec{u}\ \in\ \R^n\ |\  \vec{u}\sdot\vec{s}=0\ \forall\ \vec{s} \in S$

<u>Thm 8.10:</u> $S$ ~ subspace of $\R^n$ $\implies$ $S^\bot$ ~ subspace of $\R^n$ 

<u>Thm 8.11:</u> Let $\mathcal{V} = \{ \vec{s}_1, ..., \vec{s}_k \}$ be a basis for subspace $S$ and $\vec{u}$ be a vector. 
					Then $ \vec{u}\sdot\vec{s}_1=0,  \vec{u}\sdot\vec{s}_2 = 0, ...,  \vec{u}\sdot\vec{s}_k=0 \iff \vec{u} \in S^\bot$

<u>How to:</u> find a basis for $S^\bot$, given $S=span\{\begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}, \begin{bmatrix} -1 \\ 0 \\ 2 \end{bmatrix}\}$: (think of this as a 2D plane in $\R^3$)
		a. Make the basis vectors for $S$ into rows of a matrix
		b. Because $A\vec{u}=\begin{bmatrix} \vec{s}_1\sdot\vec{u} \\  \vec{s}_2\sdot\vec{u} \end{bmatrix}$, $\vec{u}$ is in $S^\bot$ only when $A\vec{u} = \vec{0}$
		c. Solve out $A\vec{u} = \vec{0}$, and find something like $\vec{u} = t_1\begin{bmatrix} 2 \\ -3 \\ 1 \end{bmatrix}$
		d. $S^\bot = \text{span}\{\begin{bmatrix} 2 \\ -3 \\ 1 \end{bmatrix}\}$

<u>Definition:</u> A set of vectors $\mathcal{V}$ in $\R^n$ form an orthogonal set if $\vec{v}_i \sdot \vec{v}_j = 0,\ \forall\ \vec{v}_i$ & $\vec{v}_j$ in $\mathcal{V}$, with $i \neq j$
		a. All of the vectors in the set must be orthogonal to each other 

<u>How to:</u> check if a set of vectors is orthogonal?
		a. Take the dot product of each possible pair, and if *all* are 0, then set is orthogonal

<u>Thm 8.13:</u> An orthogonal set of nonzero vectors is linearly *in*dependent

<u>Definition:</u> Orthogonal basis of a subspace is a *basis* which is also an *orthogonal* set

<u>Thm 8:14:</u> If $S$ is a subspace w/ orthogonal basis $=\{\vec{v}_1,...,\vec{v}_k\} \subseteq \R^n$, 
		Then $\forall\ \vec{s} \in S$: $\vec{s}=c_1\vec{v}_1+...+c_k\vec{v}_k$, where $c_i = \frac{\vec{s} \sdot \vec{v}_i}{||\vec{v}_i||^2}$

<u>How to:</u> express $\vec{s}$ as a linear combination of a given orthogonal vector basis:
		a. Use Thm 8.14 to get a $c_i$ for each vector in the basis, and the result will be something like $\vec{s} = -2\vec{v}_1 + \vec{v}_2$

### 8.2 Projection

<u>Definition:</u> Projection of $\vec{u}$ onto $\vec{v}$: $\text{proj}_v\vec{u}=\frac{\vec{u} \sdot \vec{v}}{||\vec{v}||^2}\vec{v}$

<u>Thm 8.16:</u> For a projection when $\vec{v}$ is nonzero:
		a. $\text{proj}_v\vec{u}$ lies on $span\{\vec{v}\}$
		b. $\vec{u}-\text{proj}_v\vec{u}$ is orthogonal to $\vec{u}$
		c. if $\vec{u}$ is in $\text{span}\{\vec{v}\}$, then $\text{proj}_v\vec{u} = \vec{u}$
		d. $\text{proj}_v\vec{u}$ = $\text{proj}_{cv}\vec{u}$

<u>Definition:</u> Let $S$ be a nonzero subspace w/ orthogonal basis $=\{\vec{v}_1,...,\vec{v}_k\}$ :
				$\text{proj}_s\vec{u} = \text{proj}_{\vec{v}_1}\vec{u}\ +\ ...\ +\ \text{proj}_{\vec{v}_k}\vec{u}$

<u>Thm 8.18:</u> For a projection on subspace when $S$ is nonzero:
		a. $\text{proj}_s\vec{u}$ lies in $S$
		b. $\vec{u}-\text{proj}_s\vec{u}$ is orthogonal to $S$
		c. If $\vec{u}$ is in $S$, then $\text{proj}_S\vec{u} = \vec{u}$
		d. $\text{proj}_s\vec{u}$ is independent of the choice of the orthogonal basis of $S$

###### Gram-Schmidt Processes

<u>Thm 8.19</u>: Let $S$ be a subspace with basis $\{\vec{s}_1, ... ,\vec{s}_k$ \}. $\vec{v}_1, \vec{v}_2, ..., \vec{v}_k$ is defined as:
		$\vec{v}_1 = \vec{s}_1$
		$\vec{v}_2 = \vec{s}_2 - \text{proj}_{\vec{v}_1}\vec{s}_2$
		$\vec{v}_3 = \vec{s}_3 - \text{proj}_{\vec{v}_1}\vec{s}_3 - \text{proj}_{\vec{v}_2}\vec{s}_3$
		$\vec{v}_k = \vec{s}_k - \text{proj}_{\vec{v}_1}\vec{s}_k - \text{proj}_{\vec{v}_2}\vec{s}_k-...-\text{proj}_{\vec{v}_{k-1}}\vec{s}_k$
		(The pattern here is that the row defining the $i$th vector uses the original basis vector $\vec{s}_i$ on that row only.
		 The vertical columns are unique to each orthogonal vector, that is to say,  column 1 is always nothing, column 2 is $\vec{v}_1$, and column k is $\vec{v}_{k-1}$   $\leftarrow$ you're recursively defining the next vector)

​		<u>Intuition:</u> The basis vectors of $S$ are already linearly independent, so you know that none of them are parallel to the others. We start off with the first basis vector of $S$ becoming the first orthogonal basis vector $\vec{v}_1$. We can find a basis vector orthogonal to that by taking the second basis vector, and subtracting off it's projection onto the previous vector to define the new orthogonal basis vector $\vec{v}_2$ (because we know that difference will be orthogonal) . We can keep going for all the basis vectors, such that $span\{\vec{v}_1, \vec{v}_2, ..., \vec{v}_k\} = span\{\vec{u}_1, \vec{u}_2, ..., \vec{u}_k\}$, then not only are the $\vec{v}$ vectors defining the same subspace, but they also are orthogonal to each other.

<u>Definition:</u> A set of vectors $\{\vec{w}_1, \vec{w}_2, ..., \vec{w}_k\}$ is orthonormal IF the set is orthogonal AND $||\vec{w}_j||=1\ \forall\ j=1,2,\dots,k$
			$\vec{w}_j = \frac{1}{||\vec{v}_j||}\vec{v}_j$ for $j=1,2,\dots,k$

<u>How to:</u> Find a set of orthonormal basis vectors from a given set of basis vectors i.e. $\{\vec{u}_1, \vec{u}_2, \vec{u}_3\}$
		a. Orthogonalize $\{\vec{u}_1, \vec{u}_2, \vec{u}_3\}$ using GS process to o
		b. Normalize to obtain an orthonormal basis of $span\{\vec{u}_1, \vec{u}_2, \vec{u}_3\}$

### 8.3 Diagonalizing Symmetric Matrices

<u>Thm 8.21</u> If $A$ ~ symmetric matrix, $\implies$ then the eigenvectors associated w/ distinct eigenvalues are orthogonal

<u>Definition:</u> $P$ ~ square, $n\text{x}n$ with orthonormal columns is called an orthogonal matrix
		\*Cols must be ortho*normal*, not just orthogonal
		$\implies P^TP=I_n$

<u>Thm 8.23:</u> If $P$ ~ $n\text{x}n$, orthonormal, $\implies$ then $P^{-1}=P^T$

<u>How to:</u> Check if a given matrix $A$ is orthogonal:
		a. Check that dot products of the columns are $0$
		b. Check that the norm of each column is $1$

<u>Definition</u> $A$ ~ *orthogonally* diagonalizable if there exists an *orthogonal* matrix $P$ and a diagonal matrix $D$ s.t. $A=PDP^{-1} = PDP^{T}$ 
		$P$ represents the *change of basis matrix* from the standard basis into the one defined by the eigenvectors

<u>Spectral Thm 8.26</u> $A$ ~ orthogonally diagonalizable $\iff$ $A$ ~ symmetric
		a. $\implies$ All eigenvalues of a symmetric matrix $A$ are real
		b. Each eigenspace of a symmetric matrix $A$ has dimension *equal* to the multiplicity of the associated eigenvalue

<u>How to:</u> Orthogonally diagonalize a matrix A:
		a. Get characteristic equation of $det(A-\lambda I_n)$, find eigenvalues
		b. Find eigenvectors for each eigenvalue (these are all orthogonal to other eigenvectors, but may not be within the same eigenspace)
		c. Apply Gram-Schmidt process to orthogonalize $\vec{u}_1, \vec{u}_2$ in a common eigenspace (do this step for every eigenspace)
		d. Normalize the the orthogonal set of vectors (even the ones from $\text{dim }1$)
		e. Construct $D$ normally, construct $P$ using the corresponding orthonormal eigenvectors, and write inverse of $P$ as $P^T$. (Make sure to position eigenvectors s.t. $P$ is symmetrical)		

<u>Thm 8.27:</u> If $A$ ~ real matrix, $\implies$ then $A^TA$ has nonnegative eigenvalues
		Note: this works on $2x3$ matrices, for example
		$A^TA$ is always symmetric $\implies$ all the stuff from this 	chapter holds, plus the fact that the eigenvalues are nonnegative

## Ch 10

### 10.1 Inner Products

<u>Definition</u>: Inner product on $V$ is a function that takes two *vectors* in $V$ as input and produces a *scalar* as output, and is denoted by $\langle \vec{u}, \vec{v} \rangle$. It must satisfy:
		a. $\langle \vec{u}, \vec{v} \rangle = \langle \vec{v}, \vec{u} \rangle$
		b. $\langle \vec{u}+\vec{v}, \vec{w} \rangle = \langle \vec{u}, \vec{w} \rangle + \langle \vec{v}, \vec{w} \rangle$
		c. $\langle c\vec{u}, \vec{v} \rangle = \langle \vec{u}, \vec{cv} \rangle = c\langle \vec{u}, \vec{v} \rangle$
		d. $\langle \vec{u}, \vec{u} \rangle \geq 0$, and $\langle \vec{u}, \vec{u} = 0\rangle$ only when $\vec{u}=0$

​	Dot product is an inner product on $\R^n$, it could also be "weighted" by some third param $t_i$ for every $u_i$ and $v_i$ in $\vec{u}\sdot\vec{v}$

<u>Definition</u>: $\vec{u} and \vec{v}$ are orthogonal $\iff \langle \vec{u}, \vec{v} \rangle =0$

<u>Definition</u>: The norm of $\vec{v}$:   $||\vec{v}||=\sqrt{\langle \vec{v}, \vec{v} \rangle}$
		a. Distance between vectors: $||\vec{u}-\vec{v}||$
		b. Norm of $\vec{cv} = |c|\ ||\vec{u}||$

<u>Pythagorean Thm 10.4</u>: $\vec{u}$ and $\vec{v}$ are orthogonal $\iff$ $||\vec{u}||^2 + ||\vec{v}||^2 = ||\vec{u}+\vec{v}||^2$

<u>Definition</u>: Projection of $\vec{u}$ onto $\vec{v}$: $\text{proj}_{\vec{v}}\vec{u} = \frac{\langle \vec{u}, \vec{v} \rangle}{\langle \vec{v}, \vec{v} \rangle}\vec{v} = \frac{\langle \vec{u}, \vec{v} \rangle}{||\vec{v}||^2}\vec{v}$

<u>Thm 10.6</u>: For a projection when $\vec{v} \text{ and } c$ is nonzero:
		a. $\text{proj}_v\vec{u}$ lies on $span\{\vec{v}\}$
		b. $\vec{u}-\text{proj}_v\vec{u}$ is orthogonal to $\vec{v}$
		c. if $\vec{u}$ is in $\text{span}\{\vec{v}\}$, then $\text{proj}_v\vec{u} = \vec{u}$
		d. $\text{proj}_v\vec{u}$ = $\text{proj}_{cv}\vec{u}$

<u>Cauchy-Schwarz Inequality Thm 10.7:</u> 	 $|\langle \vec{u}, \vec{v} \rangle| \leq ||\vec{u}||\text{ }||\vec{v}||$

<u>Triangle Inequality Thm 10.8</u> 	$||\vec{u} + \vec{v}|| \leq ||\vec{u}||+||\vec{v}||$

### 10.2 Gram-Schmidt Revisted

<u>Definition:</u> Vectors $ \{  \vec{v}_1, \dots, \vec{v)_k  \} $ in an inner product space $V$ form an orthogonal set if $ \langle \vec{v}_i, \vec{v}_j \rangle = 0 $ for $i \neq j$

<u>Definition:</u> If $\mathcal{V} = \{ \vec{v}_1, \dots, \vec{v)_k \}$ is an orthogonal set of nonzero vectors in inner product space $V$, $\implies$ then $\mathcal{V}$ is linearly *in*dependent

<u>How to:</u>   find orthonormal basis of a given basis:
		a. Do GS process to a new set of orthogonal basis vectors
		b. Normalize each one by dividing by the norms

<u>Definition:</u>

<u>Definition:</u>

<u>Definition:</u>

<u>Definition:</u>


