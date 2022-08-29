## Chapter 2

```ad-note
$$ max(f(\vec{x})) = -min(-f(\vec{x})) $$

```

![[max-min-opt.excalidraw|800]]

```ad-note
Αν το $\vec{x}$ είναι τοπικός βελτιστοποιητής της $f$, τότε πρέπει να ισχύει $\nabla{f(\vec{x}^*)} = 0$
Αν $\nabla{f(\vec{x}^*)} = 0$, αυτό **δεν** σημαίνει ότι το $\vec{x}$ είναι τοπικός βελτιστοποιητής της $f$.
```

![[grad-anti-opt.excalidraw|800]]

```ad-note
Ο $\nabla^2f(\vec{x})$ μπορεί να γραφτεί στην αντίστοιχη *τετραγωνική μορφή* (quadratic form):

$Qf(\vec{p}) : X \subset R^n \rightarrow R, Qf(\vec{p})(x) = x^T\nabla^2f(p)x = \sum_{i=1}^{n}\sum_{j=1}^{n}\frac{\partial^2f(p)}{\partial x_i\partial x_j}x_i x_j$

```

```ad-note
Ο $\nabla^2$ ονομάζεται:

- *θετικά ορισμένος*, όταν $Qf(p)(x)>0, \forall x \in R^n$, με $x\neq 0$
- *αρνητικά ορισμένος*, όταν $Qf(p)(x)<0, \forall x \in R^n$, με $x \neq 0$ 
- *θετικά ημιορισμένος*, όταν $Qf(p)(x)\ge 0, \forall x \in R^n$
- *αρνητικά ημιορισμένος*, όταν $Qf(p)(x)\le 0, \forall x \in R^n$
- *αόριστος*, όταν υπάρχουν $u, v \in R^n$ με $Qf(p)(u)>0$ και $Qf(p)(v)<0$
```

```ad-important
1. Αν ο $\nabla^2f(x^*)$ είναι *θετικά ορισμένος* τότε το $x^*$ είναι *τοπικός ελαχιστοποιητής* της $f$
2. Αν ο $\nabla^2f(x^*)$ είναι *αρνητικά ορισμένος* τότε το $x^*$ είναι *τοπικός βελτιστοποιητής* της $f$
3. Αν ο $\nabla^2f(x^*)$ είναι *αόριστος* τότε το $x^*$ *δεν* είναι τοπικός βελτιστοποιητής της $f$
```

```ad-note
Αν το $\vec{x}^*$ είναι τοπικός ελαχιστοποιητής (ή μεγιστοποιητής) της $f$, τότε πρέπει να ο $\nabla^2f(\vec{x}^*)$ να μην είναι αόριστος

```

```ad-summary
Για τοπικούς βελτιστοποιητές συνάρτησης:

1. **Κρίσιμα σημεία**: Υπολογίζω πρώτες μερικές παραγώγους για να υπολογίσω την $\nabla$ της $f$, μετά λύνω $\nabla f = \begin{bmatrix} 0 & 0 & 0\end{bmatrix}^T$
2. **Εσσιανός**: Υπολογίζω δεύτερες μερικές παραγώγους για να υπολογίσω τον $\nabla^2$ της $f$
3. Αντικαθιστώ στον $\nabla^2$ για κάθε κρίσιμο σημείο
4. Πολλαπλασιάζω με $x_i x_j$ και αθροίζω για να πάρω την τετραγωνική μορφή $Q$
```

```ad-example
Βρείτε τους τοπικούς βελτιστοποιητές της συνάρτησης $f(x_1, x_2, x_3) = x^3_1 + x_1 x^2_3 + 3x^2_1 + x^2_2 + 2x^2_3$.

**(1)** Πρώτες μερικές παράγωγοι: 

- $fx_1 = 3x^2_1 + x^2_3 + 6x_1$,
- $fx_2 = 2x_2$,
- $fx_3 = 2x_1 x_3 + 4x_3$

Κρίσιμα σημεία: $\nabla f = \begin{bmatrix}3x^2_1 + x^2_3 + 6x_1 & 2x_2 & 2x_1 x_3 + 4x_3\end{bmatrix}^T = \begin{bmatrix}0 & 0 & 0\end{bmatrix}^T$. 

- $2x_2 = 0 \Rightarrow x_2 = 0$, 
- $2x_1 x_3 + 4x_3 = 0 \Rightarrow 2x_3(x_1 + 2) = 0 \Rightarrow x_3 = 0 \lor x_1 = 0 \lor x_1 = -2$

Άρα, $x^*_\alpha = \begin{bmatrix}0 & 0 & 0\end{bmatrix}^T$ και $x^*_\beta = \begin{bmatrix}-2 & 0 & 0\end{bmatrix}^T$

**(2)** Δεύτερες μερικές παράγωγοι:

- $fx_1 x_1 = 6x_1 + 6$
- $fx_1 x_2 = fx_2 x_1 = 0$
- $fx_1 x_3 = fx_3 x_1 = 2x_3$
- $fx_2 x_2 = 2$
- $fx_2 x_3 = fx_3 x_2 = 0$
- $fx_3 x_3 = 2x_1 + 4$

Άρα, $\nabla^2f = \mathit{H} = \begin{bmatrix}6x_1 + 6 & 0 & 2x_3 \\ 0 & 2 & 0 \\ 2x_3 & 0 & 2x_1 + 4\end{bmatrix}$

**(3)** Αντικαθιστώ για $x^*_\alpha$ και για $x^*_\beta$:

- $\mathit{H}(x^*_\alpha) = \begin{bmatrix}6 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 4\end{bmatrix}$

- $\mathit{H}(x^*_\beta) = \begin{bmatrix}-6 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 0\end{bmatrix}$
  
**(4)** Πολλαπλασιάζω με $x_i x_j$ και αθροίζω για την τετραγωνική μορφή $\mathit{Q} = \textbf{x}^T\nabla^2f\textbf(p){x}$:

- $\mathit{Q}(x^*_\alpha)(x_1, x_2, x_3) = 6x^2_1 + 2x^2_2 + 4x^2_3 > 0, \forall (x_1, x_2, x_3) \ne \begin{pmatrix}0 & 0 & 0\end{pmatrix}$ 
- $\mathit{Q}(x^*_\beta)(x_1, x_2, x_3) = -6x^2_1 + 2x^2_2$, παρατηρώ ότι, π.χ., $\mathit{Q}(x^*_\beta)(1, 0, 0) < 0$, ενώ $\mathit{Q}(x^*_\beta)(0, 1, 0) > 0$

Επομένως, ο $x^*_\alpha$ είναι *τοπικός ελαχιστοποιητής* της $f$, ενώ ο $x^*_\beta$ *δεν* είναι τοπικός βελτιστοποιητής της συνάρτησης $f$.
```

```ad-note
*Πρωτεύουσες ελάσσονες ορίζουσες* του Εσσιανού πίνακα $\nabla^2f(p)$:

$\Delta_1 = \frac{\partial^2f(p)}{\partial x^2_1}$,

$\Delta_2 = \begin{vmatrix}\frac{\partial^2f(p)}{\partial x^2_1} & \frac{\partial^2f(p)}{\partial x_1\partial x_2}\\ \frac{\partial^2f(p)}{\partial x_2 x_1} & \frac{\partial^2f(p)}{\partial x^2_2}\end{vmatrix}$

$\Delta_3 = \begin{vmatrix}\frac{\partial^2f(p)}{\partial x^2_1} & \frac{\partial^2f(p)}{\partial x_1\partial x_2} & \frac{\partial^2f(p)}{\partial x_1\partial x_3}\\ \frac{\partial^2f(p)}{\partial x_2 x_1} & \frac{\partial^2f(p)}{\partial x^2_2} & \frac{\partial^2f(p)}{\partial x_2 x_3}\\ \frac{\partial^2f(p)}{\partial x_3 x_1} & \frac{\partial^2f(p)}{\partial x_3\partial x_2} & \frac{\partial^2f(p)}{\partial x^2_3}\end{vmatrix}$

$\vdots$

$\Delta_n = |\nabla^2f(p)|$
```

```ad-important
1. Αν $\Delta_k > 0$ $\forall k = 1, \dots, n$ τότε το $x^*$ είναι *τοπικός ελαχιστοποιητής* της $f$
2. Αν $(-1)^k\Delta_k > 0$ $\forall k = 1, \dots, n$, δηλαδή αν $\Delta_1 < 0$, $\Delta_2 > 0$, $\Delta_3 < 0$, $\Delta_4 > 0$, $\dots$ τότε το $x^*$ είναι *τοπικός μεγιστοποιητής* της $f$
3. Αν $\Delta_k < 0$ για κάποιο $k$ *άρτιο* με $k = 1, \dots, n$ τότε το $x^*$ *δεν* είναι τοπικός βελτιστοποιητής της $f$
4. Αν $\Delta_k \ne 0$ $\forall k = 1, \dots, n$ και το σύνολο $\begin{Bmatrix}\Delta_1, \frac{\Delta_2}{\Delta_1}, \frac{\Delta_3}{\Delta_2}, \dots, \frac{\Delta_n}{\Delta_{n-1}}\end{Bmatrix}$ περιέχει θετικά *και* αρνητικά στοιχεία τότε το $x^*$ *δεν* είναι τοπικός βελτιστοποιητής της $f$
```

```ad-summary
Για τοπικούς βελτιστοποιητές συνάρτησης:

1. **Κρίσιμα σημεία**: Υπολογίζω πρώτες μερικές παραγώγους για να υπολογίσω την $\nabla$ της $f$, μετά λύνω $\nabla f = \begin{bmatrix} 0 & 0 & 0\end{bmatrix}^T$
2. **Εσσιανός**: Υπολογίζω δεύτερες μερικές παραγώγους για να υπολογίσω τον $\nabla^2$ της $f$
3. **Πρωτεύουσες ελάσσονες ορίζουσες**: Υπολογίζω με βάση τον Εσσιανό
4. Αντικαθιστώ στις ορίζουσες για κάθε κρίσιμο σημείο
```

```ad-example
Βρείτε τους τοπικούς βελτιστοποιητές της συνάρτησης
$f(x_1, x_2) = x^3_1 - 3x^2_1 + x^2_2$

**(1)** Πρώτες μερικές παράγωγοι: 

- $fx_1 = 3x^2_1 - 6x_1$,
- $fx_2 = 2x_2$

Κρίσιμα σημεία: $\nabla f = \begin{bmatrix}3x^2_1 - 6x_1 & 2x_2\end{bmatrix}^T = \begin{bmatrix}0 & 0\end{bmatrix}^T$. 

- $2x_2 = 0 \Rightarrow x_2 = 0$, 
- $3x^2_1 - 6x_1 = 0 \Rightarrow 3x_1(x_1 - 2) = 0 \Rightarrow x_1 = 0 \lor x_1 = 2$

Άρα, $x^*_\alpha = \begin{bmatrix}0 & 0\end{bmatrix}^T$ και $x^*_\beta = \begin{bmatrix}2 & 0\end{bmatrix}^T$

**(2)** Δεύτερες μερικές παράγωγοι:

- $fx_1 x_1 = 6x_1 - 6$
- $fx_1 x_2 = fx_2 x_1 = 0$
- $fx_2 x_2 = 2$

Άρα, $\nabla^2f = \mathit{H} = \begin{bmatrix}6x_1 - 6 & 0\\ 0 & 2\end{bmatrix}$

**(3)** Υπολογίζω τις πρωτεύουσες ελάσσονες ορίζουσες:

- $\Delta_1 = 6x_1 - x$
- $\Delta_2 = 12x_1 - 12$

**(4)** Αντικαθιστώ για $x^*_\alpha$ και για $x^*_\beta$:

- $\Delta_1(x^*_\alpha) = -6 < 0$, $\Delta_2(x^*_\alpha) = -12 < 0$
- $\Delta_1(x^*_\beta) = 6 > 0$, $\Delta_2(x^*_\beta) = 12 > 0$

Επομένως, ο $x^*_\alpha$ *δεν* είναι τοπικός βελτιστοποιητής της $f$, ενώ ο $x^*_\beta$ είναι *τοπικός ελαχιστοποιητής* της συνάρτησης $f$.
```

```ad-example
Βρείτε τους τοπικούς βελτιστοποιητές της συνάρτησης
$f(x_1, x_2) = \frac{1}{3}x^3_1 + \frac{1}{2}x^2_1 + 2x_1 x_2 + \frac{1}{2}x^2_2 - x_2 + 9$

**(1)** Πρώτες μερικές παράγωγοι: 

- $fx_1 = x^2_1 + x_1 + 2x_2$,
- $fx_2 = 2x_1 + x_2 - 1$

Κρίσιμα σημεία: $\nabla f = \begin{bmatrix}x^2_1 + x_1 + 2x_2 & 2x_1 + x_2 - 1\end{bmatrix}^T = \begin{bmatrix}0 & 0\end{bmatrix}^T$. 

- $2x_1 + x_2 - 1 = 0 \Rightarrow x_2 = 1 - 2x_1 \Rightarrow x^2_1 + x_1 + 2 - 4x_1 = 0 \Rightarrow x^2_1 - 3x_1 + 2 = 0$, διακρίνουσα $\Delta = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} = \frac{3 \pm \sqrt{1}}{2} \Rightarrow x_1 = 2 \lor x_1 = 1$  
- Αντικαθιστώ στην $2x_1 + x_2 -1$ για $x_1 = 2$: $4 + x_2 - 1 = 0 \Rightarrow x_2 = -3$, και για $x_1 = 1$: $2 + x_2 - 1 = 0 \Rightarrow x_2 = -1$

Άρα, $x^*_\alpha = \begin{bmatrix}1 & -1\end{bmatrix}^T$ και $x^*_\beta = \begin{bmatrix}2 & -3\end{bmatrix}^T$

**(2)** Δεύτερες μερικές παράγωγοι:

- $fx_1 x_1 = 2x_1 + 1$
- $fx_1 x_2 = fx_2 x_1 = 2$
- $fx_2 x_2 = 1$

Άρα, $\nabla^2f = \mathit{H} = \begin{bmatrix}2x_1 + 1 & 2\\ 2 & 1\end{bmatrix}$

**(3)** Υπολογίζω τις πρωτεύουσες ελάσσονες ορίζουσες:

- $\Delta_1 = 2x_1 + 1$
- $\Delta_2 = 2x_1 +1 - 4 = 2x_1 - 3$

**(4)** Αντικαθιστώ για $x^*_\alpha$ και για $x^*_\beta$:

- $\Delta_1(x^*_\alpha) = 3 > 0$, $\Delta_2(x^*_\alpha) = -1 < 0$
- $\Delta_1(x^*_\beta) = 5 > 0$, $\Delta_2(x^*_\beta) = 1 > 0$

Επομένως, ο $x^*_\alpha$ *δεν* είναι τοπικός βελτιστοποιητής της $f$, ενώ ο $x^*_\beta$ είναι *τοπικός ελαχιστοποιητής* της συνάρτησης $f$.
```

```ad-important
1. Αν οι ιδιοτιμές του $\nabla^2f(x^*)$ είναι θετικές, τότε το $x^*$ είναι *τοπικός ελαχιστοποιητής* της $f$
2. Αν οι ιδιοτιμές του $\nabla^2f(x^*)$ είναι αρνητικές, τότε το $x^*$ είναι *τοπικός μεγιστοποιητής* της $f$
3. Αν ο $\nabla^2f(x^*)$ έχει μία (τουλάχιστον) θετική ιδιοτιμή και μία (τουλάχιστον) αρνητική ιδιοτιμή τότε το $x^*$ *δεν* είναι τοπικός βελτιστοποιητής της $f$
```

```ad-example
Βρείτε τους τοπικούς βελτιστοποιητές της συνάρτησης
$f(x_1, x_2, x_3) = x^3_1 + x^2_2 + x^2_3 - 3x_1$

**(1)** Πρώτες μερικές παράγωγοι: 

- $fx_1 = 3x^2_1 - 3$,
- $fx_2 = 2x_2$
- $fx_3 = 2x_3$

Κρίσιμα σημεία: $\nabla f = \begin{bmatrix}3x^2_1 - 3 & 2x_2 & 2x_3\end{bmatrix}^T = \begin{bmatrix}0 & 0 & 0\end{bmatrix}^T$. 

- $2x_2 = 0 \Rightarrow x_2 = 0$
- $2x_3 = 0 \Rightarrow x_3 = 0$
- $3x^2_1 - 3 = 0 \Rightarrow 3x^2_1 = 3 \Rightarrow x_1 = -1 \lor x_1 = 1$

Άρα, $x^*_\alpha = \begin{bmatrix}-1 & 0 & 0\end{bmatrix}^T$ και $x^*_\beta = \begin{bmatrix}1 & 0 & 0\end{bmatrix}^T$

**(2)** Δεύτερες μερικές παράγωγοι:

- $fx_1 x_1 = 6x_1$
- $fx_1 x_2 = fx_2 x_1 = 0$
- $fx_1 x_3 = fx_3 x_1 = 0$
- $fx_2 x_2 = 2$
- $fx_2 x_3 = fx_3 x_2 = 0$
- $fx_3 x_3 = 2$

Άρα, $\nabla^2f = \mathit{H} = \begin{bmatrix}6x_1 & 0 & 0\\ 0 & 2 & 0\\ 0 & 0 & 2\end{bmatrix}$

**(3)** Αντικαθιστώ για $x^*_\alpha$ και για $x^*_\beta$:

Ιδιοτιμές:

- $\lambda_1(x^*_\alpha) = -6 < 0$, $\lambda_2(x^*_\alpha) = 2 > 0$, $\lambda_3(x^*_\alpha) = 2 > 0$
- $\lambda_1(x^*_\beta) = 6 > 0$, $\lambda_2(x^*_\beta) = 2 > 0$, $\lambda_3(x^*_\beta) = 2 > 0$

Επομένως, ο $x^*_\alpha$ *δεν* είναι τοπικός βελτιστοποιητής της $f$, ενώ ο $x^*_\beta$ είναι *τοπικός ελαχιστοποιητής* της συνάρτησης $f$.
```

## Chapter 3

