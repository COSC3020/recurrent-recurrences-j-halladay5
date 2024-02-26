[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Substitute to find general pattern : $\ T(\frac{n}{13}) + 5 => T(\frac{n}{13^2}) + 10  =>  T(\frac{n}{13^i}) + (5i) $ 

Plug in $\ i = log_{13} n  : T(\frac{n}{13^{log_{13} n}}) + (5 \cdot \log_{13} n) =>  T(n) + 5log_{13} n$

$\ 1 + 5log_{13} n \in \Theta(log n)$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Substitute: $\ 13 T(\frac{n}{13}) + 5 => 13 ( 13 T(\frac{n}{13^2}) + 5) + 5 => 13^2 T(\frac{n}{13^2}) + 70 $

$$\ 13^i T(\frac{n}{13^i}) + \sum_{j=0}^{i-1} 5 \cdot 13^j $$

Plug in $$\ i= log_{13} n : 13^{log_{13} n} T(\frac{n}{13^{log_{13} n}}) + \sum_{j=0}^{log_{13} n -1} 5 \cdot 13^{log_{13} n -1} => n \cdot T(n) + 5n $$

$\ 6n \in \Theta(n) $

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

Substitute: $\ 13 T(\frac{n}{13}) + 2n => 13 ( 13T(\frac{n}{13^2}) + 2(\frac{n}{13})) + 2n => 13^2 T(\frac{n}{13^2}) + 4n => 13^i T(\frac{n}{13^i}) + (2ni) $

Plug in i = log_{13} n : $\ n * T(1) + (2n \cdot log_{13} n) => n + 2nlog_{13} n) $

$\ n + 2nlog_{13} n \in \Theta(nlog n)$
