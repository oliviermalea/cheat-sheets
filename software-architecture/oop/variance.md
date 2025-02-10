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


## Définition canonique
La variance, la covariance et la contravariance sont des concepts utilisés en statistiques et en algèbre linéaire. Ils sont souvent employés dans le domaine des probabilités, de l'analyse de données et de la théorie des matrices. Voici des explications succinctes pour chaque concept :

1. **Variance :**
   - La variance mesure la dispersion des valeurs d'une variable aléatoire par rapport à sa moyenne.
   - Elle est calculée en prenant la moyenne des carrés des écarts entre chaque valeur et la moyenne.
   - Une variance élevée indique une grande dispersion des données, tandis qu'une variance faible indique une faible dispersion.

2. **Covariance :**
   - La covariance mesure la relation linéaire entre deux variables aléatoires.
   - Elle est calculée en prenant la moyenne des produits des écarts de chaque variable par rapport à leur moyenne respective.
   - Une covariance positive indique une tendance à augmenter ou diminuer simultanément, tandis qu'une covariance négative indique une tendance à varier en sens opposé.

3. **Contravariance :**
   - La contravariance n'est pas un concept aussi standard que la variance et la covariance. Il semble y avoir une confusion ici, car le terme "contravariance" est plus couramment associé à des concepts en programmation et en génie logiciel, particulièrement en relation avec les types de données dans les langages de programmation orientés objet.
   - En programmation, la contravariance se réfère à la possibilité d'utiliser un type de données moins spécifique que celui attendu. Cela signifie qu'un objet d'un type moins dérivé peut être utilisé là où un objet du type attendu est requis.
   
En résumé, la variance et la covariance sont principalement des concepts statistiques, tandis que la contravariance est plus couramment associée à des concepts de programmation.