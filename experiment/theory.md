<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<!-- MathJax v3 CDN -->
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async
        src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>
</head>
<body>
      <div class="px-6 pb-6 flex-1">
        <div
          class="w-full text-[#007bff] font-normal text-[19.2px]"
          style="font-family: Raleway, sans-serif"
        ><p>In signal processing, basic matrices play crucial roles in various operations, forming the backbone of many algorithms and techniques. The identity matrix, a specific type of diagonal matrix, serves as a neutral element in matrix multiplication, crucial for preserving original signal values during transformations. Diagonal matrices streamline computations by allowing for independent scaling of signal components. Singular Value Decomposition (SVD) is a powerful tool in signal processing, extensively applied in noise reduction, data compression, and system identification. Matrix multiplication is fundamental in filtering, convolution, and applying linear transformations to signals, with convolution matrices specifically used to represent the effect of filters or kernels on signals.</p>
        <p>The Fourier matrix is essential for converting signals between time and frequency domains in signal processing. Transposition is used in forming cross-correlation matrices and working with orthogonal bases, like in PCA. Determinants help analyze system stability and calculate volumes in multivariate Gaussian distributions, while eigenvalue decomposition simplifies the representation of systems and signal energy distribution.</p>
        <p>LU decomposition is essential for solving linear equations, inverting matrices, and computing determinants. In signal processing, linear equations are crucial for various tasks, including filter design, system identification, and signal reconstruction. They are used to model and solve problems such as noise reduction, linear filtering, and Fourier transforms. Linear systems also underpin techniques like Principal Component Analysis (PCA) and Kalman filtering for estimation and prediction. Essentially, they provide the mathematical framework for manipulating and analyzing signals efficiently.</p>
        <p>Row echelon form is a fundamental tool in linear algebra that supports various signal processing applications by simplifying the analysis and solution of linear systems, determining matrix rank, etc.</p>
        <p>These foundational matrices enable efficient computation, representation, and manipulation of signals, serving as the building blocks for more complex signal processing tasks.</p>
        </div></div>
<br/><br/>
  <h2>Properties of Matrix Operations</h2>
  <h2>Properties of Matrix Addition</h2>
  <p>The fundamental properties of real number addition also apply to matrices.</p>
  <p>Let \( A \), \( B \), and \( C \) be \( m \times n \) matrices:</p>
  <ol>
    <li><strong>Commutative Property</strong>: \( A + B = B + A \)</li>
    <li><strong>Associative Property</strong>: \( A + (B + C) = (A + B) + C \)</li>
    <li><strong>Additive Identity</strong>: There exists a unique \( m \times n \) zero matrix \( O \) such that \( A + O = A \)</li>
    <li><strong>Additive Inverse</strong>: For every matrix \( A \), there exists \( -A \) such that \( A + (-A) = O \)</li>
  </ol>
  <h2>Properties of Matrix Multiplication</h2>
  <p>Unlike addition, not all multiplication properties of real numbers apply to matrices.</p>
  <ul>
    <li>Matrix multiplication is <strong>not commutative</strong>: Even if both \( AB \) and \( BA \) are defined, they may not be equal.</li>
    <li>A matrix may not have a <strong>multiplicative inverse</strong>, even if it is square.</li>
  </ul>
  <p>However, some properties <strong>do generalize</strong>. Let \( A \), \( B \), and \( C \) be matrices such that the operations are defined:</p>
  <ol>
    <li><strong>Associative Property</strong>: \( A(BC) = (AB)C \)</li>
    <li><strong>Left Distributive Property</strong>: \( A(B + C) = AB + AC \)</li>
    <li><strong>Right Distributive Property</strong>: \( (A + B)C = AC + BC \)</li>
    <li><strong>Multiplicative Identity</strong>: \( I_m A = A \), \( A I_n = A \)</li>
  </ol>
  <h2>Properties of Scalar Multiplication</h2>
  <p>Let \( r \), \( s \) be real numbers, and \( A \), \( B \) be matrices:</p>
  <ol>
    <li>\( r(sA) = (rs)A \)</li>
    <li>\( (r + s)A = rA + sA \)</li>
    <li>\( r(A + B) = rA + rB \)</li>
    <li>\( A(rB) = r(AB) = (rA)B \) (if defined)</li>
  </ol>
  <h2>Properties of the Transpose of a Matrix</h2>
  <p>Let \( r \) be real, and \( A \), \( B \) be matrices:</p>
  <ol>
    <li>\( (A^T)^T = A \)</li>
    <li>\( (A + B)^T = A^T + B^T \)</li>
    <li>\( (AB)^T = B^T A^T \)</li>
    <li>\( (rA)^T = rA^T \)</li>
  </ol>
  <h2>Properties of Determinants</h2>
  <ol>
    <li>\( \det(A) = \det(A^T) \)</li>
    <li>If any row/column is multiplied by \( k \), then \( \det(\Delta') = k \cdot \det(\Delta) \)</li>
    <li>If a row or column is all zeros, then \( \det = 0 \)</li>
    <li>If matrix is upper/lower triangular, \( \det = \) product of diagonal elements</li>
  </ol>

<h2>Matrix Theory: Minor, Cofactor, Adjoint, and Inverse</h2>

<h2>Matrix Multiplication Representation</h2>
<p>Let matrix \( A \) be of size \( i \times k \), and matrix \( B \) be of size \( k \times j \). Their product \( C = A \cdot B \) will result in a matrix of size \( i \times j \).</p>
<p>The element in the \( i^{\text{th}} \) row and \( j^{\text{th}} \) column of the resulting matrix \( C \), denoted by \( c_{ij} \), is calculated as:</p>
<p>\( c_{ij} = \sum_k a_{ik} \cdot b_{kj} \)</p>
<p>The transpose of matrix \( C \), denoted as \( C^T \), swaps rows and columns, resulting in a matrix of size \( j \times i \):</p>
<p>\( C^T = [C]_{j \times i} \), where \( C^T_{ji} = C_{ij} \)</p>

<h2>1. Transpose of a Product</h2>

<h3>1.a. Proof that \( (AB)^T = B^T A^T \)</h3>
<p>The transpose of a product of two matrices equals the product of their transposes in reverse order. That is:</p>
<p>\( (AB)^T = B^T A^T \)</p>
<p>To see why this is true, consider the element at position \( (i, j) \) in \( (AB)^T \):</p>
<p>\( (AB)^T_{ij} = (AB)_{ji} = \sum_k a_{jk} \cdot b_{ki} \)</p>
<p>On the other hand, consider the element \( (i, j) \) in \( B^T A^T \):</p>
<p>\( (B^T A^T)_{ij} = \sum_k b^T_{ik} \cdot a^T_{kj} = \sum_k b_{ki} \cdot a_{jk} \)</p>
<p>Since both expressions are the same, we conclude:</p>
<p>\( (AB)^T = B^T A^T \)</p>

<h3>1.b. Reverse Direction \( B^T A^T = (AB)^T \)</h3>
<p>We can also prove this identity starting from the right-hand side:</p>
<p>\( (B^T A^T)_{ij} = \sum_k b^T_{ik} \cdot a^T_{kj} = \sum_k b_{ki} \cdot a_{jk} = (AB)_{ji} = (AB)^T_{ij} \)</p>

<h2>2. Cofactor and Adjoint</h2>

<h3>Cofactor Matrix</h3>
<p>The cofactor of the element in the \( i^{\text{th}} \) row and \( j^{\text{th}} \) column of a square matrix \( A \) is given by:</p>
<p>\( \text{CO}_{ij} = (-1)^{i+j} \cdot M_{ij} \)</p>
<p>Where \( M_{ij} \) is the <strong>minor</strong> of the element, i.e., the determinant of the submatrix formed by deleting the \( i^{\text{th}} \) row and \( j^{\text{th}} \) column from \( A \).</p>

<h3>Adjoint</h3>
<p>The adjoint (or adjugate) of a square matrix \( A \) is the transpose of the matrix of cofactors:</p>
<p>\( \text{Adj}(A) = [\text{CO}_{ij}]^T \)</p>

<h2>3. Inverse of a Matrix</h2>
<p>If matrix \( A \) is invertible (i.e., \( \det(A) \ne 0 \)), then the inverse of \( A \) is given by:</p>
<p>\( A^{-1} = \frac{\text{Adj}(A)}{\det(A)} \)</p>

<h2>4. Inverse of a Product</h2>
<p>The inverse of a product of two invertible matrices is the product of their inverses in reverse order:</p>
<p>\( (AB)^{-1} = B^{-1} A^{-1} \)</p>
<p><strong>Proof:</strong></p>
<p>Start with the identity:</p>
<p>\( (AB)(AB)^{-1} = I \)</p>
<p>Pre-multiply both sides by \( A^{-1} \):</p>
<p>\( A^{-1}(AB)(AB)^{-1} = A^{-1} \Rightarrow B(AB)^{-1} = A^{-1} \)</p>
<p>Now pre-multiply both sides by \( B^{-1} \):</p>
<p>\( B^{-1}B(AB)^{-1} = B^{-1}A^{-1} \Rightarrow (AB)^{-1} = B^{-1}A^{-1} \)</p>

<h2>5. Adjoint of a Product</h2>
<p>The adjoint of the product of two matrices equals the product of their adjoints in reverse order:</p>
<p>\( \text{Adj}(AB) = \text{Adj}(B) \cdot \text{Adj}(A) \)</p>

<p><strong>Why this works:</strong></p>
<p>From the inverse formula:</p>
<p>\( (AB)^{-1} = \frac{\text{Adj}(AB)}{\det(AB)} \)</p>
<p>We also have:</p>
<p>\( (AB)^{-1} = B^{-1} A^{-1} \), and \( \det(AB) = \det(A) \cdot \det(B) \)</p>
<p>Substitute the inverse formulas:</p>
<p>\( A^{-1} = \frac{\text{Adj}(A)}{\det(A)} \), and \( B^{-1} = \frac{\text{Adj}(B)}{\det(B)} \)</p>
<p>Multiply the adjoints accordingly:</p>
<p>\( \text{Adj}(B) \cdot \text{Adj}(A) = \det(A) \cdot \det(B) \cdot B^{-1} \cdot A^{-1} \)</p>
<p>Thus, from the original inverse formula:</p>
<p>\( \text{Adj}(AB) = \text{Adj}(B) \cdot \text{Adj}(A) \)</p>

<h2 id = "ev">Eigenvalue and Eigenvector</h2>
			<p>
				Let’s assume a square matrix <strong>A</strong>
			</p>
			<p>
				The characteristic equation,
			</p>
			<p>
				<strong>| A – </strong>λ*<strong>I | = </strong>0&#xa0;&#xa0; 
			</p>
			<p>
				<em>(where </em><strong><em>I </em></strong><em>is an identity matrix)</em>
			</p>
			<p>
				After calculating the values of λs we attempt to find eigenvectors for corresponding eigenvalues like this
			</p>
			<p>
				For eigenvalue, λ = λ<sub>1</sub>
			</p>
			<p>
				<strong>A*x</strong> = λ<sub>1</sub>*<strong>I*x</strong><strong>&#xa0;&#xa0; </strong><em>(where, </em><strong><em>x</em></strong><em> is an unknown vector)</em>
			</p>
			<p>
				Or, (<strong>A</strong> - λ<sub>1</sub>*<strong>I</strong>)*<strong>x</strong> = 0
			</p>
			<p>
				The value of <strong>x </strong>is the corresponding eigenvector of λ<sub>1</sub>
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>Power Method for Dominant Eigenvalue</strong>
			</p>
			<p>
				Let λ<sub>1</sub>, λ<sub>2</sub>, λ<sub>3</sub>, and λ<sub>n</sub> be the eigenvalues of an <strong>n X n </strong>matrix <strong>A</strong>.&#xa0; λ<sub>1 </sub>is called the dominant eigenvalue of <strong>A</strong> if
			</p>
			<p>
				| λ<sub>1</sub>| &gt; | λ<sub>i </sub>|,&#xa0;&#xa0; <em>i = 2, 3, ... , n</em>
			</p>
			<p>
				The eigenvectors corresponding to λ<sub>1 </sub>are called dominant eigenvectors of <strong>A</strong>.
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>Example</strong>
			</p>
			<p>
				A = <img src="1739254504_matrix-theory/1739254504_matrix-theory-7.png" width="82" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				We begin with an initial nonzero approximation of
			</p>
			<p>
				<strong>x</strong><strong><sub>0</sub></strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-8.png" width="24" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				We then obtain the following approximations
			</p>
			<p>
				<strong>x</strong><strong><sub>1</sub></strong><strong> = Ax</strong><strong><sub>0 </sub></strong><strong>= </strong><img src="1739254504_matrix-theory/1739254504_matrix-theory-9.png" width="106" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-10.png" width="53" height="42" alt="" /> = -4<img src="1739254504_matrix-theory/1739254504_matrix-theory-11.png" width="49" height="42" alt="" />
			</p>
			<p>
				<strong>&#xa0;</strong>
			</p>
			<p>
				<strong>x</strong><strong><sub>2</sub></strong><strong> = Ax</strong><strong><sub>1 </sub></strong><strong>= </strong><img src="1739254504_matrix-theory/1739254504_matrix-theory-12.png" width="134" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-13.png" width="35" height="42" alt="" /> = 10<img src="1739254504_matrix-theory/1739254504_matrix-theory-14.png" width="49" height="42" alt="" />
			</p>
			<p>
				<strong>x</strong><strong><sub>3</sub></strong><strong> = Ax</strong><strong><sub>2 </sub></strong><strong>= </strong><img src="1739254504_matrix-theory/1739254504_matrix-theory-15.png" width="116" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-16.png" width="53" height="42" alt="" /> = -22<img src="1739254504_matrix-theory/1739254504_matrix-theory-17.png" width="49" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>x</strong><strong><sub>4</sub></strong><strong> = Ax</strong><strong><sub>3 </sub></strong><strong>= </strong><img src="1739254504_matrix-theory/1739254504_matrix-theory-18.png" width="134" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-19.png" width="45" height="42" alt="" /> = 46<img src="1739254504_matrix-theory/1739254504_matrix-theory-20.png" width="49" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>x</strong><strong><sub>5</sub></strong><strong> = Ax</strong><strong><sub>4 </sub></strong><strong>= </strong><img src="1739254504_matrix-theory/1739254504_matrix-theory-21.png" width="127" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-22.png" width="63" height="42" alt="" /> = -94<img src="1739254504_matrix-theory/1739254504_matrix-theory-23.png" width="49" height="42" alt="" />
			</p>
			<p>
				<strong>x</strong><strong><sub>6</sub></strong><strong> = Ax</strong><strong><sub>5 </sub></strong><strong>= </strong><img src="1739254504_matrix-theory/1739254504_matrix-theory-24.png" width="145" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-25.png" width="45" height="42" alt="" /> = 190<img src="1739254504_matrix-theory/1739254504_matrix-theory-26.png" width="49" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Note that the approximations in Example appear to be approaching scalar multiples of <img src="1739254504_matrix-theory/1739254504_matrix-theory-27.png" width="24" height="42" alt="" />
			</p>
			<p>
				So, the obtained dominant eigenvector from the above iterations is
			</p>
			<p>
				<strong>x</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-27.png" width="24" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Now, we’ll find the corresponding eigenvalue from the obtained eigenvector
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>Formula</strong>
			</p>
			<p>
				If <strong>x </strong>is an eigenvector of <strong>A</strong>, then its corresponding eigenvalue is given by 
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				λ = (<strong>Ax.x / x.x</strong>)
			</p>
			<p>
				<strong>Ax </strong>= <img src="1739254504_matrix-theory/1739254504_matrix-theory-28.png" width="130" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-29.png" width="67" height="42" alt="" />
			</p>
			<p>
				Then, <strong>Ax.x = </strong><img src="1739254504_matrix-theory/1739254504_matrix-theory-30.png" width="116" height="42" alt="" /> = -20.0 (approx.)
			</p>
			<p>
				And <strong>x.x </strong>= <img src="1739254504_matrix-theory/1739254504_matrix-theory-31.png" width="97" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-26.png" width="49" height="42" alt="" /> = 9.94 (approx.)
			</p>
			<p>
				So, the corresponding eigenvalue, λ = (-20.0 / 9.94) = -2 (approx.)
			</p>
			<p>
				&#xa0;
			</p>
			<h2 id = "svd">Singular Value Decomposition (SVD)</h2>
			<p>
				<strong>Theory:</strong>
			</p>
			<p>
				Singular Value Decomposition (SVD) is a matrix factorization technique that decomposes any m×n matrix A into three matrices: A=UΣV<sup>T</sup> 
			</p>
			<p>
				Where:
			</p>
			<ul>
				<li>
					U is an m×m orthogonal matrix (or unitary if complex).
				</li>
				<li>
					Σ is m×n diagonal matrix with non-negative real numbers on the diagonal (singular values).
				</li>
				<li>
					V<sup>T</sup> is an n×n orthogonal matrix (or unitary if complex), and V<sup>T</sup> is the transpose of V.
				</li>
			</ul>
			<p>
				<strong>Example</strong>
			</p>
			<p>
				A = <img src="1739254504_matrix-theory/1739254504_matrix-theory-32.png" width="53" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Compute A<sup>T</sup>A and AA<sup>T</sup>
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				A<sup>T</sup>A = <img src="1739254504_matrix-theory/1739254504_matrix-theory-33.png" width="111" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-34.png" width="74" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				AA<sup>T</sup> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-35.png" width="111" height="42" alt="" /> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-36.png" width="74" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>Find Eigenvalues and Eigenvectors</strong>:
			</p>
			<p>
				For A<sup>T</sup>A:
			</p>
			<ul>
				<li>
					Eigenvalues are λ1= 29.8661 and λ2 = 0.1339
				</li>
				<li>
					Corresponding eigenvectors (normalized) are v1 = <img src="1739254504_matrix-theory/1739254504_matrix-theory-37.png" width="92" height="42" alt="" />and v2 = <img src="1739254504_matrix-theory/1739254504_matrix-theory-38.png" width="88" height="42" alt="" />
				</li>
			</ul>
			<p>
				For AA<sup>T</sup>:
			</p>
			<ul>
				<li>
					Eigenvalues are λ1= 29.8661 and λ2 = 0.1339
				</li>
				<li>
					Corresponding eigenvectors (normalized) are u1 = <img src="1739254504_matrix-theory/1739254504_matrix-theory-39.png" width="92" height="42" alt="" />and u2 = <img src="1739254504_matrix-theory/1739254504_matrix-theory-40.png" width="88" height="42" alt="" />
				</li>
			</ul>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>Compute Singular Values</strong>:
			</p>
			<p>
				Singular values are σ1 = √ 29.8661= 5.4650
			</p>
			<p>
				And σ1 = √ 0.1339 = 0.3660
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>Final SVD:</strong>
			</p>
			<p>
				A=UΣV<sup>T</sup>
			</p>
			<p>
				Where: 
			</p>
			<p>
				U = <img src="1739254504_matrix-theory/1739254504_matrix-theory-41.png" width="185" height="42" alt="" />&#xa0; Σ = <img src="1739254504_matrix-theory/1739254504_matrix-theory-42.png" width="149" height="42" alt="" />&#xa0; 
			</p>
			<p>
				V<sup>T</sup> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-43.png" width="180" height="42" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<h2 id = "lu">LU Decomposition</h2>
			<p>
				LU Decomposition is a method to find solutions of linear equations.
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Using Gauss Elimination Method 
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Consider a matrix&#xa0;𝐴. If all entries below the diagonal entries are zero, then the matrix is called “upper triangular.” If all entries above the diagonal entries are zero, then the matrix is called “lower triangular.” 
			</p>
			<p>
				&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0; And <strong>A = L*U</strong>
			</p>
			<p>
				<strong>L</strong> =<img src="1739254504_matrix-theory/1739254504_matrix-theory-44.png" width="201" height="79" alt="" />&#xa0; ;&#xa0;&#xa0; <strong>U</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-45.png" width="178" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong><em>L= lower triangular matrix; U= upper triangular matrix</em></strong>
			</p>
			<p>
				&#xa0;
			</p>
			<ol start="5">
				<li>
					For a given matrix
				</li>
			</ol>
			<p>
				<strong>A</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-46.png" width="186" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>A=L*U</strong>
			</p>
			<p>
				Or, <strong>A</strong>=<img src="1739254504_matrix-theory/1739254504_matrix-theory-47.png" width="117" height="79" alt="" />* <img src="1739254504_matrix-theory/1739254504_matrix-theory-46.png" width="186" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong><em>L= lower triangular matrix; U= upper triangular matrix</em></strong>
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				After doing the row&#xa0;operation "R2 - (-2)*R1," we get,
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Or, <strong>A</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-48.png" width="135" height="79" alt="" />* <img src="1739254504_matrix-theory/1739254504_matrix-theory-49.png" width="142" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				After row operation in matrix <strong>U</strong>, we've set (-2) to the same place of the<strong> L</strong> matrix and the (2, 1)<sup>th</sup> position of the U matrix, which is now zero.
			</p>
			<p>
				Firstly, try the first column elements of matrix <strong>U</strong> below diagonal elements to make zeroes,
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				After doing,&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0; ‘R2-(-2)*R1’ <em>(as demonstrated above)</em>
			</p>
			<p>
				&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0; ‘R3-(3)*R1’ and
			</p>
			<p>
				&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0; ‘R4-(2)*R1’
			</p>
			<p>
				We get,
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>A</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-50.png" width="135" height="79" alt="" />* <img src="1739254504_matrix-theory/1739254504_matrix-theory-51.png" width="167" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				In a same way, we will now employ row operations to set the elements of the second column of matrix <strong>U</strong> to zero.
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Calculate,&#xa0;&#xa0;&#xa0; ‘R3-(-4)*R2’ and
			</p>
			<p>
				&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0;&#xa0; ‘R4-(1)*R2’
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				We get,
			</p>
			<p>
				<strong>A</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-52.png" width="153" height="79" alt="" />* <img src="1739254504_matrix-theory/1739254504_matrix-theory-53.png" width="149" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Now, we'll apply row operations to convert the elements of the third column of matrix <strong>U</strong> to zeroes.
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				Now calculate "R4-(3)*R2"
			</p>
			<p>
				We get,
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>A</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-54.png" width="153" height="79" alt="" />* <img src="1739254504_matrix-theory/1739254504_matrix-theory-55.png" width="149" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				So, 
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>L</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-54.png" width="153" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>U</strong> = <img src="1739254504_matrix-theory/1739254504_matrix-theory-55.png" width="149" height="79" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<ol start="6">
				<li>
					<strong>Before showing the final result, all intermediate steps must be displayed.</strong>
				</li>
			</ol>
			<p>
				&#xa0;
			</p>
			<h2>Row Echelon Form</h2>
			<p>
				A matrix is in row echelon form if
			</p>
			<ul>
				<li>
					All rows consisting of only zeroes are at the bottom.
				</li>
				<li>
					The leading entry (that is the left-most nonzero entry) of every nonzero row is to the right of the leading entry of every row above
				</li>
				<li>
					Some texts add the condition that the leading coefficient must be 1 while others regard this as reduced row echelon form
				</li>
				<li>
					These two conditions imply that all entries in a column below a leading coefficient are zeros
				</li>
			</ul>
			<p>
				&#xa0;
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>Example</strong>
			</p>
			<p>
				Given matrix,
			</p>
			<p>
				<strong>A = </strong><img src="1739254504_matrix-theory/1739254504_matrix-theory-56.png" width="104" height="61" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				R2 ← R2 – R1
			</p>
			<p>
				<img src="1739254504_matrix-theory/1739254504_matrix-theory-57.png" width="100" height="61" alt="" />
			</p>
			<p>
				<strong>&#xa0;</strong>
			</p>
			<p>
				R3 ← R3 + 2*R2
			</p>
			<p>
				<img src="1739254504_matrix-theory/1739254504_matrix-theory-58.png" width="100" height="61" alt="" />
			</p>
			<p>
				<strong>&#xa0;</strong>
			</p>
			<p>
				R3 ← R3 / 4
			</p>
			<p>
				<img src="1739254504_matrix-theory/1739254504_matrix-theory-59.png" width="100" height="61" alt="" />
			</p>
			<p>
				&#xa0;
			</p>
			<h2>Rank of a Matrix</h2>
			<p>
				<strong>Theory:</strong>
			</p>
			<p>
				<strong>Definition</strong>: The rank of a matrix is defined as the maximum number of linearly independent rows (or columns) in the matrix. It can also be seen as the dimension of the row space or column space of the matrix.
			</p>
			<p>
				&#xa0;
			</p>
			<p>
				<strong>Rank of a Matrix in Row Echelon Form (REF)</strong>
			</p>
			<ol>
				<li>
					<strong>Row Echelon Form (REF)</strong>: A matrix is in row echelon form when:
					<ul>
						<li>
							All non-zero rows are above any rows of all zeros.
						</li>
						<li>
							The leading entry (pivot) of each non-zero row is to the right of the leading entry of the row above it.
						</li>
						<li>
							All entries below a pivot are zero.
						</li>
					</ul>
				</li>
			</ol>
			<p>
				&#xa0;
			</p>
			<ol start="2">
				<li>
					<strong>Finding the Rank</strong>:
					<ul>
						<li>
							<strong>Identify Non-Zero Rows</strong>: In REF, the rank of the matrix is equal to the number of non-zero rows. This is because each non-zero row represents a linearly independent vector in the row space of the matrix.
						</li>
						<li>
							<strong>Process</strong>: Convert the matrix to REF using row operations (row swapping, scaling rows, adding/subtracting multiples of rows) and count the number of non-zero rows to determine the rank.
						</li>
					</ul>
				</li>
			</ol>
			<p>
				&#xa0;
			</p>
</body>
</html>
