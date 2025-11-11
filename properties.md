  <h2 id = "properties">Properties of Matrix Operations</h2>
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