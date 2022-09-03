# Chapter 4

```ad-abstract
$x_{k+1} = x_k - \alpha_k \begin{bmatrix}\nabla^2 f(x_k)\end{bmatrix}^{-1}\nabla f(x_k)$


```

```ad-important
Μέθοδος Newton: $x_{k+1} = x_k - \alpha_k \begin{bmatrix}\nabla^2 f(x_k)\end{bmatrix}^{-1}\nabla f(x_k)$

Δηλαδή, η μέθοδος Newton εφαρμόζεται για την αναζήτηση τοπικού ελαχιστοποιητή στην κατεύθυνση
$p_k = -\begin{bmatrix}\nabla^2 f(x_k)\end{bmatrix}^{-1}\nabla f(x_k)$
```

```ad-important
**Αλγόριθμος Newton**

**(1) Αρχικοποίηση**: Επιλογή αρχικής πρόβλεψης (αρχικού διανύσματος) $x_0$ και ορισμός σταθεράς τερματισμού $\epsilon > 0$ και $k = 0$

**(2) Κύριο βήμα**:

- Αν $||\nabla f(x_k)|| < \epsilon$ τότε ο αλγόριθμος τερματίζεται και η προσεγγιστική τιμή του βελτιστοποιητή είναι η $x_k$
- Διαφορετικά, υπολογίζουμε τον $\nabla^2f(x_k)$ και την κατεύθυνση αναζήτησης $\begin{bmatrix}\nabla^2 f(x_k)\end{bmatrix}p_k = -\nabla f(x_k)$ ή $p_k = -\begin{bmatrix}\nabla^2 f(x_k)\end{bmatrix}^{-1}\nabla f(x_k)$
- Προσδιορίζουμε ένα βήμα μήκους $\alpha_k$ που ελαχιστοποιεί τη συνάρτηση $\phi(\alpha_k) = f(x_k + \alpha_k p_k)$ ως προς $\alpha_k > 0$
- Προσδιορίζουμε τη βελτιωμένη εκτίμηση της λύσης του προβλήματος $x_{k+1} = x_k + \alpha_k p_k$
- Επαναλαμβάνουμε το κύριο βήμα για το $k + 1$
```

```ad-note
TODO: Cholesky, etc.
```

```ad-note
TODO: summary on how to solve exercise
```

```ad-summary
TODO
```