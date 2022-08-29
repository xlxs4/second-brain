| Name                                   | Date | Hour  | Place |
| -------------------------------------- | ---- | ----- | ----- |
| Βελτιστοποίηση                         | 15/9 | 08:15 | Δ11   |
| Ανάλυση II                             | 14/9 | 11:30 | Δ11   |
| Επικοινωνία Ανθρώπου ΗΥ                | 19/9 | 11:30 | Δ11   |

---

# Opt
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
