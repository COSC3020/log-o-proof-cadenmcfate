[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/fbkbKZ5N)
# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

## Proof:

$\exists c,n_0: \log_2 n \le c \cdot \log_5 n \forall n \geq n_0$

$\Rightarrow \exists n_0: \log_2 n \le \frac{1}{\log_5 2} \cdot \log_5 n \forall n \geq n_0$ &emsp;&emsp;&emsp;
$(c\rightarrow \frac{1}{\log_5 2})$

$\Rightarrow \exists n_0: \log_2 n \le \log_2 n \forall n \geq n_0$ &emsp;&emsp;&emsp;(definition of log base conversion)

$\Rightarrow \log_2 n \le \log_2 n \forall n \geq 1$ &emsp;&emsp;&emsp;
$(n\rightarrow 1)$

$\Rightarrow \log_2 n \in O(\log_5 n)$  &emsp;&emsp;&emsp;(definition of O)


And


$\exists c,n_0: \log_5 n \le c \cdot \log_2 n \forall n \geq n_0$

$\Rightarrow \exists n_0: \log_5 n \le \frac{1}{\log_2 5} \cdot \log_2 n \forall n \geq n_0$ &emsp;&emsp;&emsp;
$(c\rightarrow \frac{1}{\log_2 5})$

$\Rightarrow \exists n_0: \log_5 n \le \log_5 n \forall n \geq n_0$ &emsp;&emsp;&emsp;(definition of log base conversion)

$\Rightarrow \log_5 n \le \log_5 n \forall n \geq 1$ &emsp;&emsp;&emsp;
$(n\rightarrow 1)$

$\Rightarrow \log_5 n \in O(\log_2 n)$  &emsp;&emsp;&emsp;(definition of O)

Thus, $O(\log_{2} n)$ is the same as $O(\log_{5} n)$ because $\log_5 n \in O(\log_2 n)$ and $\log_2 n \in O(\log_5 n)$. Intuitively this makes sense because the change of base formula for logarithms only involves a constant term in the denominator. In this case we can take, for example, a search function for a 5-ary tree and a binary tree. We now know that the difference in complexity would be constant, and they will have the same asymptotic complexities.

