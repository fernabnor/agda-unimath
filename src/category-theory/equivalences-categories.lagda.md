# Equivalences between categories

```agda
module category-theory.equivalences-categories where
```

<details><summary>Imports</summary>

```agda
open import category-theory.categories
open import category-theory.equivalences-precategories
open import category-theory.functors-categories

open import foundation.universe-levels
```

</details>

## Idea

A functor `F : C → D` on categories is an equivalence if it is an equivalence on
the underlying precategories.

## Definition

```agda
module _
  {l1 l2 l3 l4 : Level}
  (C : Category l1 l2)
  (D : Category l3 l4)
  where

  is-equiv-functor-Category : functor-Category C D → UU (l1 ⊔ l2 ⊔ l3 ⊔ l4)
  is-equiv-functor-Category =
    is-equiv-functor-Precategory
      ( precategory-Category C)
      ( precategory-Category D)

  equiv-Category : UU (l1 ⊔ l2 ⊔ l3 ⊔ l4)
  equiv-Category =
    equiv-Precategory (precategory-Category C) (precategory-Category D)
```
