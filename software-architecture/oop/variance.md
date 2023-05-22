# Variance

Variance refers to how subtyping between more complex types relates to [subtyping](https://en.wikipedia.org/wiki/Subtyping) between their components.

For example, assuming the type Cat is a subtype of Animal, then an expression of type Cat should be substitutable wherever an expression of type Animal is used.

---

## Covariance and Contravariance (computer science)

**Covariance** is the quality of being different by being more specific _(Cat is covariant to Animal)_ while **Contravariance** is the quality of being different by being more general _(Animal is contravariant to Cat)_.

---

## Postel's law

In programming, Postel's Law relates to [covariance and contravariance](https://en.wikipedia.org/wiki/Covariance_and_contravariance_(computer_science)). Functions and APIs may be contravariant with respect to their inputs, but covariant with respect to their outputs.

see : <https://deviq.com/laws/postels-law>

Postel's Law, also known as the robustness principle, states:

- _Be conservative in what you do, be liberal in what you accept from others._

Jon Postel wrote this in an early version of the TCP specification in 1980, and it has since been referred to as Postel's Law.

The main goal of this principle is to maximize the tolerance individual components of a system have for small incompatibilities.
