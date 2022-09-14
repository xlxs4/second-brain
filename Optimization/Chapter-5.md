# Chapter 5

```ad-note
Πολλαπλασιαστής Lagrange $\lambda^*$:
$$\nabla f(\vec{x^*}) = \lambda^* \nabla g(\vec{x^*})$$
```

```ad-example
Βρείτε τη δεσμευμένη μέγιστη και ελάχιστη τιμή της συνάρτησης
$$f(x_1, x_2) = x^3_1 + x^3_2$$
υπό τη δέσμευση
$$g(x_1, x_2) = x^2_1 + x^2_2 - 4 = 0$$

---

- $fx_1 = 3x^2_1$
- $fx_2 = 3x^2_2$
- $gx_1 = 2x_1$
- $gx_2 = 2x_2$

Άρα $\nabla f = \begin{bmatrix}3x^2_1 & 3x^2_2\end{bmatrix}$ και $\nabla g = \begin{bmatrix}2x_1 & 2x_2\end{bmatrix}$

Από τον πολλαπλασιαστή Lagrange, έχουμε:

$\nabla f = \lambda\nabla g$ και $g(x_1, x_2) = 0$ $\Rightarrow 3x^2_1 = 2\lambda 
 x_1, 3x^2_2 = 2\lambda x_2, x^2_1 + x^2_2 = 4 \Rightarrow x_1(3x_1 - 2\lambda) = 0, x_2(3x_2 - 2\lambda) = 0, x^2_1 + x^2_2 = 4 \Rightarrow$
- $x_1 = 0, x_2 = \frac{2}{3}\lambda, \begin{pmatrix}\frac{2}{3}\lambda\end{pmatrix}^2 = 4 \Rightarrow \lambda = \pm 3$
- $x_1 = \frac{2}{3}\lambda, x_2 = 0, \begin{pmatrix}\frac{2}{3}\lambda\end{pmatrix}^2 = 4 \Rightarrow \lambda = \pm 3$
- $x_1 = \frac{2}{3}\lambda, x_2 = \frac{2}{3}\lambda, 2\begin{pmatrix}\frac{2}{3}\lambda\end{pmatrix}^2 = 4 \Rightarrow \lambda = \pm \frac{3}{\sqrt{2}}$

Άρα, έχουμε λύσεις $(x_1, x_2, \lambda) = (0, 2, 3), (0, -2, -3), (2, 0, 3), (-2, 0, -3), (\sqrt{2}, \sqrt{2}, \frac{3}{\sqrt{2}}), (\sqrt{2}, \sqrt{2}, \frac{-3}{\sqrt{2}})$

Δεσμευμένα κρίσιμα σημεία της f:
- $\vec{x^*_1} = \begin{bmatrix}0 & 2\end{bmatrix}^T$
- $\vec{x^*_2} = \begin{bmatrix}0 & -2\end{bmatrix}^T$
- $\vec{x^*_3} = \begin{bmatrix}2 & 0\end{bmatrix}^T$
- $\vec{x^*_4} = \begin{bmatrix}-2 & 0\end{bmatrix}^T$
- $\vec{x^*_5} = \begin{bmatrix}\sqrt{2} & \sqrt{2}\end{bmatrix}^T$
- $\vec{x^*_6} = \begin{bmatrix}-\sqrt{2} & -\sqrt{2}\end{bmatrix}^T$

Με τιμές:
- $f(\vec{x^*_1}) = 8$
- $f(\vec{x^*_2}) = -8$
- $f(\vec{x^*_3}) = 8$
- $f(\vec{x^*_4}) = -8$
- $f(\vec{x^*_5}) = 4\sqrt{2}$
- $f(\vec{x^*_6}) = -4\sqrt{2}$

Το εφικτό σύνολο $\Omega = {(x_1, x_2) \in \mathit{R}^2, x^2_1 + x^2_2 = 4}$ είναι κλειστό και φραγμένο, άρα:

- Δεσμευμένη μέγιστη τιμή της $f$: $8$
- Δεσμευμένη ελάχιστη τιμή της $f$: $-8$
- Δεσμευμένοι τοπικοί ελαχιστοποιητές: $\vec{x^*_2}, \: \vec{x^*_4}$
- Δεσμευμένοι τοπικοί μεγιστοποιητές: $\vec{x^*_1}, \: \vec{x^*_3}$
```
```ad-example
Βρείτε τα σημεία δεσμευμένων τοπικών ακροτάτων της
$$f(x_1, x_2, x_3) = x^2_1 + x^2_2 + x^2_3$$
υπό τη δέσμευση
$$g(x_1, x_2, x_3) = x_1 + x_2 + x_3 - 1 = 0$$

---

$f, \: g \: C^2$ στο $\mathit{R}^2$

- $fx_1 = 2x_1$
- $fx_2 = 2x_2$
- $fx_3 = 2x_3$

- $fx_1 x_1 = 2$
- $fx_1 x_2 = fx_2 x_1 = 0$
- $fx_1 x_3 = 0$
- $fx_2 x_2 = 2$
- $fx_2 x_3 = fx_3 x_2 = 0$
- $fx_3 x_3 = 2$

- $gx_1 = 1$
- $gx_2 = 1$
- $gx_3 = 1$

$\mathit{H} = \nabla^2f = \begin{bmatrix}2 & 0 & 0\\ 0 & 2 & 0\\ 0 & 0 & 2\end{bmatrix}$

Από πολλαπλασιαστή Lagrange:
$$\nabla f(\vec{x}) - \lambda \nabla g(\vec{x}) = 0 \land g(\vec{x}) = 0 \Rightarrow (2x_1 - \lambda, 2x_2 - \lambda, 2x_3 - \lambda) = 0 \land x_1 + x_2 + x_3 = 1$$

- $2x_1 = \lambda \Rightarrow x_1 = \frac{1}{3}$
- $2x_2 = \lambda \Rightarrow x_2 = \frac{1}{3}$
- $2x_3 = \lambda \Rightarrow x_3 = \frac{1}{3}$
- $x_1 + x_2 + x_3 = 1 \Rightarrow \lambda = \frac{2}{3}$

$$\Rightarrow (\vec{x}^*, \lambda^*) = \begin{pmatrix}\frac{1}{3} & \frac{1}{3} & \frac{1}{3} & \frac{2}{3}\end{pmatrix} = \frac{1}{3}\begin{pmatrix}1 & 1 & 1 & 2\end{pmatrix}$$

$$\nabla^2\mathit{L}(\vec{x}^*, \lambda^*) = \begin{bmatrix}2 & 0 & 0 & -1\\ 0 & 2 & 0 & -1\\ 0 & 0 & 2 & -1\\ -1 & -1 & -1 & 0\end{bmatrix}$$

- $\Delta_3 = 8 > 0$
- $\Delta_4 = -12 < 0$

Άρα, το $\vec{x}^* = \begin{bmatrix}\frac{1}{3} & \frac{1}{3} & \frac{1}{3}\end{bmatrix}^T$ είναι δεσμευμένο τοπικό μέγιστο της $f$
```
