# Chapter 6

```ad-important
**Karush-Kuhn-Tucker** conditions:

- $\nabla_\vec{x} \mathit{L}(\vec{x^*}, \vec{\lambda^*}) = \vec{0}$ μπορεί να γραφτεί και ως $\nabla f(\vec{x^*}) - \sum \lambda_i \nabla g_i (\vec{x^*}) = 0, \: i \in A(\vec{x^*})$
- $g_i(\vec{x}) = 0, \: \forall i \in \epsilon$
- $g_i(\vec{x}) \ge 0, \: \forall i \in \mathit{I}$
- $\lambda^*_i \ge 0, \: \forall i \in \mathit{I}$
- $\lambda^*_i g_i(\vec{x^*}) = 0, \: \forall i \in \epsilon \cup \mathit{I}$
```
```ad-example
$$minimize \: f(x_1, x_2) = (x_1 - \frac{3}{2})^2 + (x_2 - \frac{1}{2}) ^ 4$$

$$s.t. \: g_1(x_1, x_2) = 1 - x_1 - x_2 \ge 0$$
$$g_2(x_1, x_2) = 1 - x_1 + x_2\ge 0$$
$$g_3(x_1, x_2) = 1 + x_1 - x_2\ge 0$$
$$g_4(x_1, x_2) = 1 + x_1 + x_2\ge 0$$

---

![[chapter-6-opt.excalidraw|600]]

- $fx_1 = 2(x_1 - \frac{3}{2})$
- $fx_2 = 4(x_2 - \frac{1}{2})^3$
- $g_1 x_1 = -1$
- $g_1 x_2 = -1$
- $g_2 x_1 = -1$
- $g_2 x_2 = 1$

Το σημείο $\vec{x^*} = \begin{bmatrix}1 & 0\end{bmatrix}^T$, όπως φαίνεται και στο σχήμα, είναι ο βελτιστοποιητής. Στο $\vec{x^*}$ είναι ενεργοί μόνο οι περιορισμοί $g_1$ και $g_2$.

$$\nabla f(\vec{x}) = \begin{bmatrix}2(x_1 - \frac{3}{2}) & 4(x_2 - \frac{1}{2})^3\end{bmatrix}^T \ne \begin{bmatrix}0 & 0\end{bmatrix}^T \: \forall (x_1, x_2) \in \mathit{Int}(\Omega)$$

Στο $\vec{x^*}$:

- $\nabla f(\vec{x^*}) = \begin{bmatrix}-1 & \frac{-1}{2}\end{bmatrix}^T$
- $\nabla g_1(\vec{x^*}) = \begin{bmatrix}-1 & -1\end{bmatrix}^T$
- $\nabla g_2(\vec{x^*}) = \begin{bmatrix}-1 & 1\end{bmatrix}^T$

Οι Karush-Kuhn-Tucker συνθήκες ικανοποιούνται στο $\vec{x^*}$ για

$$\vec{\lambda^*} = \begin{bmatrix}\frac{3}{4} & \frac{1}{4} & 0 & 0\end{bmatrix}^T$$

Όπου για τους ανενεργούς περιορισμούς $g_3$ και $g_4$ "επισυνάπτουμε" μηδενικά στο $\lambda$
```

```ad-important

```

```ad-example
$$minimize \: f(x_1, x_2) = (x_1 - 2)^2 + 2(x_2 - 1)^2$$

$$s.t. \: g_1(x_1, x_2) = 3 - x_1 - 4x_2 \ge 0$$
$$g_2(x_1, x_2) = x_1 - x_2 \ge 0$$

---

- $fx_1 = 2(x_1 - 2)$
- $fx_2 = 4(x_2 - 1)$

- $fx_1 x_1 = 2$
- $fx_1 x_2 = fx_2 x_1 = 0$
- $fx_2 x_2 = 4$

- $g_1 x_1 = -1$
- $g_1 x_2 = -4$
- $g_2 x_1 = 1$
- $g_2 x_2 = -1$

- $g_1 x_1 x_1 = 0$
- $g_1 x_1 x_2 = g_1 x_2 x_1 = 0$
- $g_1 x_2 x_2 = 0$

- $g_2 x_1 x_1 = 0$
- $g_2 x_1 x_2 = g_2 x_2 x_1 = 0$
- $g_2 x_2 x_2 = 0$

---

$$\mathit{L}(x_1, x_2, \lambda_1, \lambda_2) = f(x_1, x_2) - \lambda_1 g_1(x_1, x_2) - \lambda_2 g_2(x_1, x_2)$$

$$\nabla_{\vec{x}}\mathit{L}(x_1, x_2, \lambda_1, \lambda_2) = \begin{bmatrix}2(x_1 - 2) + \lambda_1 - \lambda_2 & 4(x_2 - 1) + 4\lambda_1 + \lambda_2\end{bmatrix}^T$$

Οι συνθήκες ΚΚΤ είναι:

- $\nabla_{\vec{x}} \mathit{L}(\vec{x^*}, \vec{\lambda^*}) = \vec{0}$
- $g_i(\vec{x^*}) = 0$
- $g_i(\vec{x^*}) \ge 0$
- $\lambda^*_i \ge 0$
- $\lambda^*_i g_i(\vec{x^*}) = 0$

Οπότε έχουμε:

$$2(x_1 - 2) + \lambda_1 - \lambda_2 = 0$$
$$4(x_2 - 1) + 4\lambda_1 + \lambda_2 = 0$$

---

$$3 - x_1 - 4x_2 \ge 0$$
$$x_1 - x_2 \ge 0$$

---

$$\lambda_1 \ge 0, \: \lambda_2 \ge 0$$

---

$$\lambda_1 (3 - x_1 - 4x_2) = 0$$
$$\lambda_2 (x_1 - x_2) = 0$$

Οπότε:

Από τις $\lambda_1 (3 - x_1 - 4x_2) = 0$ και $\lambda_2 (x_1 - x_2) = 0$ έχουμε:

**(1)** $\lambda_1 = 0, \: \lambda_2 = 0$ και από την $2(x_1 - 2) + \lambda_1 - \lambda_2 = 0$ έχουμε $\Rightarrow x_1 = 2$, ενώ από την $4(x_2 - 1) + 4 \lambda_1 + \lambda_2 = 0$ έχουμε $\Rightarrow x_2 = 1$

Όμως, $g_1(2, 1) = -3 > 0$, επομένως δεν πληρούνται οι ΚΚΤ και το $\begin{bmatrix}2 & 1\end{bmatrix}^T$ δεν είναι λύση του προβλήματος

**(2)** $\lambda_1 = 0, \: x_1 = x_2$, άρα $\Rightarrow 2x_1 - 4 - \lambda_2 = 0 \land 4x_1 - 4 + \lambda_2 = 0 \Rightarrow 2x_1 + 2\lambda_2 = 0 \Rightarrow x_1 = -\lambda_2 = x_2$ και, αντικαθιστώντας στην $2(x_1 - 2) + \lambda_1 - \lambda_2 = 0$ έχουμε $\Rightarrow 2x_1 - 4 + x_1 = 0 \Rightarrow 3x_1 = 4 \Rightarrow x_1 = \frac{4}{3} = x_2$, όμως $g_1(\frac{4}{3}, \frac{4}{3}) = \frac{-11}{3} < 0$, άρα και αυτή η λύση απορρίπτεται

**(3)** $\lambda_2 = 0, \: 3 - x_1 - 4x_2 = 0$, άρα $\Rightarrow x_1 + 4x_2 = 3 \Rightarrow x_1 = 3 - 4x_2$ και από την $2(x_1 - 2) + \lambda_1 = 0$ έχουμε $\Rightarrow 6 - 8 x_2 - 4 + \lambda_1 = 0 \land 4x_2 - 4 + 4\lambda_1 = 0 \Rightarrow 6 - 8x_2 = 4x_2 - 4 + 4\lambda_1 \Rightarrow 12 x_2 + 3\lambda_1 = 6 \Rightarrow 12x_2 = 6 - 3\lambda_1 \Rightarrow 6 - 12 x_2 = 3 \lambda_1$ και από την $x_1 = 3 - 4x_2$ που βρήκαμε πριν, αυτή γίνεται $\Rightarrow 2x_1 - 4x_2 = 3\lambda_1$. Έχουμε και $x_1 = 3 - 4x_2 \Rightarrow 4x_2 = 3 - x_1 \Rightarrow x_2 = \frac{3 - x_1}{4}$, άρα από την $2x_1 - 4x_2 = 3\lambda_1$ παίρνουμε $\Rightarrow 2x_1 - 4(\frac{3-x_1}{4}) = 3\lambda_1 \Rightarrow 3x_1 = 3\lambda_1 + 3 \Rightarrow x_1 = \lambda_1 + 1$ και, τέλος, από την $2(x_1 - 2) + \lambda_1 - \lambda_2 = 0$ μπορούμε να χρησιμοποιήσουμε την $x_1 = \lambda_1 + 1$ ώστε $\Rightarrow 2x_1 - 4 + x_1 = 1 \Rightarrow 3x_1 = 5 \Rightarrow x_1 = \frac{5}{3}$ και, αφού $x2 = \frac{3-x_1}{4}$, έχουμε $\Rightarrow x_2 = \frac{\frac{4}{3}}{4} \Rightarrow x_2 = \frac{1}{3}$

Παρατηρούμε ότι $g_1(\frac{5}{3}, \frac{1}{3}) = 0$, $g_2(\frac{5}{3}, \frac{1}{3}) = 0$ και $\lambda_1 = x_1 -1 = \frac{2}{3} > 0$. Άρα οι ΚΚΤ ικανοποιούνται και το $\begin{bmatrix}\frac{5}{3} & \frac{1}{3}\end{bmatrix}^T$ είναι εφικτό σημείο

**(4)** $3 - x_1 - 4x_2 = 0, \: x_1 - x_2 = 0$, άρα $x1 = x_2$ και αφού $3 - x_1 - 4x_2 = 0$, τότε $\Rightarrow 5x_1 = 3 \Rightarrow x_1 = \frac{3}{5} = x_2$

$g_1(x_1, x_2) = 0$, $g_2(x_1, x_2) = 0$

Από την $2(x_1 - 2) + \lambda_1 - \lambda_2 = 0$ έχουμε $\Rightarrow \frac{-14}{5} + \lambda_1 = \lambda_2$, αντικαθιστώντας στην $4(x_2 - 1) + 4\lambda_1 + \lambda_2 = 0$ έχουμε $\Rightarrow \frac{-8}{5} + 4\lambda_1 + \lambda_1 + \frac{-14}{5} = 0 \Rightarrow 5\lambda_1 = \frac{22}{5} \Rightarrow \lambda_1 = \frac{22}{25} > 0$, αλλά από την $\lambda_2 = \frac{-14}{5} + \lambda_1$ έχουμε ότι $\Rightarrow \lambda_2 = \frac{-14}{5} + \frac{22}{25} \Rightarrow \lambda_2 = \frac{-48}{25} < 0$, απορρίπτεται.

Επομένως, το σημείο που ικανοποιεί τις ΚΚΤ είναι το $\vec{x^*} = \begin{bmatrix}\frac{5}{3} & \frac{1}{3}\end{bmatrix}^T$

---

Για να αξιολογήσουμε το σημείο, υπολογίζουμε τον
$$\nabla^2_{\vec{x}\vec{x}}\mathit{L}(x_1, x_2, \lambda_1, \lambda_2) = \nabla^2f(x_1, x_2) - \lambda_1\nabla^2g_1(x_1, x_2) - \lambda_2\nabla^2g_2(x_1, x_2) = \nabla^2f(x_1, x_2) = \begin{bmatrix}2 & 0\\ 0 & 4\end{bmatrix}$$

Αφού $\nabla^2g_1 = 0 \land \nabla^2g_2 = 0$.

Η τετραγωνική μορφή του Εσσιανού είναι η $\vec{u}^T\nabla^2_{\vec{x}\vec{x}}\mathit{L}(x_1, x_2, \lambda_1, \lambda_2)\vec{u} = 2x^2_1 + 4x^2_2 > 0, \: \forall \vec{u} \ne \vec{0}$. Άρα ο $\nabla^2_{\vec{x}\vec{x}}\mathit{L}(x_1, x_2, \lambda_1, \lambda_2)$ είναι θετικά ορισμένος και επομένως το $\vec{x^*} = \begin{bmatrix}\frac{5}{3} & \frac{1}{3}\end{bmatrix}^T$ αποτελεί γνήσιο δεσμευμένο τοπικό ελαχιστοποιητή της $f$.
```
