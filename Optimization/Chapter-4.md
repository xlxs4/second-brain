# Chapter 4

```ad-abstract
$$x_{k+1} = x_k - \alpha_k \begin{bmatrix}\nabla^2 f(x_k)\end{bmatrix}^{-1}\nabla f(x_k)$$


```

```ad-important
Μέθοδος Newton: 
$$x_{k+1} = x_k - \alpha_k \begin{bmatrix}\nabla^2 f(x_k)\end{bmatrix}^{-1}\nabla f(x_k)$$

Δηλαδή, η μέθοδος Newton εφαρμόζεται για την αναζήτηση τοπικού ελαχιστοποιητή στην κατεύθυνση
$$p_k = -\begin{bmatrix}\nabla^2 f(x_k)\end{bmatrix}^{-1}\nabla f(x_k)$$
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
TODO: Cholesky (when positively defined!), etc.
```

```ad-note
TODO: summary on how to solve exercise
```

```ad-important
TODO: συνάρτηση με μία μεταβλητή και Newton
```

```ad-example
Προσδιορίστε τις τρεις πρώτες επαναλήψεις της μεθόδου Newton για τη λύση του προβλήματος βελτιστοποίησης
$$\textrm{minimize}\: f(x) = x^4 -1$$

Θεωρώντας το αρχικό σημείο $x_0 = 4$. Επιπλέον, προσδιορίστε αναλυτικά την ακολουθία $x_k$ της μεθόδου και αποδείξτε ότι αυτή συγκλίνει προς τον ελαχιστοποιητή $x^*$ του προβλήματος. Επίσης, υπολογίστε τον ρυθμό σύγκλισης και εξηγήστε το αποτέλεσμα

---

- $f'(x) = 4x^3$
- $f''(x) = 12x^2$

Η αναδρομική ακολουθία $x_k$ της Newton προκύπτει από

$$x_{k+1} = x_k - \frac{f'(x_k)}{f''(x_k)} = \frac{2}{3}x_k$$

Έχουμε $\begin{vmatrix}\frac{x_{k+1}}{x_k}\end{vmatrix} = \frac{2}{3} < 1$, άρα η ακολουθία $x_k$ *συγκλίνει* *για κάθε* επιλογή του αρχικού σημείου $x_0$

Επίσης, από την $x_{k+1} = \frac{2}{3}x_k$ έχουμε $x_k = \begin{pmatrix}\frac{2}{3}\end{pmatrix}^k, \: x_0 = 4\begin{pmatrix}\frac{2}{3}\end{pmatrix}^k, \: k = 0, 1, 2, \dots$

Οπότε, για τις επόμενες επαναλήψεις μπορούμε να βρούμε κατευθείαν χρησιμοποιώντας την ακολουθία:

- $x_1 = 4\cdot\frac{2}{3} = \frac{8}{3}$
- $x_2 = 4\cdot\frac{4}{9} = \frac{16}{9}$
- $x_3 = 4\cdot\frac{8}{27} = \frac{32}{27}$

Για να βρούμε τον ελαχιστοποιητή μπορούμε επομένως να υπολογίσουμε το όριο της $x_k$

$$x^* = \lim_{k\to\infty} x_k = \lim_{k\to\infty} 4 \cdot \begin{pmatrix}\frac{2}{3}\end{pmatrix}^k = 0$$

Αφού βρούμε τον ελαχιστοποιητή μπορούμε να τον χρησιμοποιήσουμε για να βρούμε τον ρυθμό σύγκλισης

$$\lim_{k\to\infty}\frac{|e_k +1|}{|e_k|} = \lim_{k\to\infty}\frac{|x_{k+1} - x^*|}{|x_k - x^*|} = \lim_{k\to\infty}\frac{|x_{k+1}|}{|x_k|} = \frac{2}{3}$$

και άρα ο ρυθμός σύγκλισης είναι γραμμικός, δηλαδή $r = 1$, και η σταθερά σύγκλισης είναι $C = \frac{2}{3}$

Η σύγκλιση είναι γραμμική και *όχι* τετραγωνική, επειδή το $x^* = 0$ είναι πολλαπλή ρίζα της $f'(x) = 0$, δηλαδή ισχύει

$$f'(x^*) = f''(x^*) = f'''(x^*) = 0$$
```

```ad-note
TODO: details on Newton, convergence, comparison with Steepest Descent
```

```ad-summary
TODO
```