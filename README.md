[![DOI](https://zenodo.org/badge/1029571863.svg)](https://doi.org/10.5281/zenodo.20825406)

# Database for Fusion Categories

This repository provides a database for fusion categories in different forms. 

## TensorCategories.jl

This database is accesible via our julia package [TensorCategories.jl](https://github.com/TensorCategories/TensorCategories.jl). Please visit the documentation for detailed information.

## AnyonWiki

The multiplicity fusion categories up to rank 7 that are contained are taken from the [AnyonWiki](https://anyonwiki.github.io). If you use the Data please cite both packages.

```julia-repl
julia> using TensorCategories;

julia> C = anyonwiki(3,1,0,2,1,1,1)
Fusion Category 3_1_0_2_1_1_1

julia> print_multiplication_table(C)
3×3 Matrix{String}:
 "𝟙"   "X2"  "X3"
 "X2"  "𝟙"   "X3"
 "X3"  "X3"  "𝟙 ⊕ X2 ⊕ X3"
```

## Centers of multiplicity-free fusion categories up to rank 5
 
We computed all centers of multiplicty free fusion categories up to rank 5 in [https://arxiv.org/abs/2406.13438](https://arxiv.org/abs/2406.13438) and stored them here. 

```julia-repl
julia> using TensorCategories

julia> Z = anyonwiki_center(3,1,0,2,1,1,1)
Skeletonization of Drinfeld center of Fusion Category 3_1_0_2_1_1_1

julia> print_multiplication_table(Z)
8×8 Matrix{String}:
 "(𝟙, γ)"        "(X2, γ)"       …  "(X2 ⊕ X3, γ)"
 "(X2, γ)"       "(𝟙, γ)"           "(𝟙 ⊕ X3, γ)"
 "(𝟙 ⊕ X2, γ)"   "(𝟙 ⊕ X2, γ)"      "(𝟙 ⊕ X3, γ) ⊕ (X2 ⊕ X3, γ)"
 "(X3, γ1)"      "(X3, γ1)"         "(𝟙 ⊕ X3, γ) ⊕ (X2 ⊕ X3, γ)"
 "(X3, γ2)"      "(X3, γ2)"         "(𝟙 ⊕ X3, γ) ⊕ (X2 ⊕ X3, γ)"
 "(X3, γ3)"      "(X3, γ3)"      …  "(𝟙 ⊕ X3, γ) ⊕ (X2 ⊕ X3, γ)"
 "(𝟙 ⊕ X3, γ)"   "(X2 ⊕ X3, γ)"     "(X2, γ) ⊕ (𝟙 ⊕ X2, γ) ⊕ (X3, γ1) ⊕ (X3, γ2) ⊕ (X3, γ3)"
 "(X2 ⊕ X3, γ)"  "(𝟙 ⊕ X3, γ)"      "(𝟙, γ) ⊕ (𝟙 ⊕ X2, γ) ⊕ (X3, γ1) ⊕ (X3, γ2) ⊕ (X3, γ3)"
```

If you use this data please cite the article as follows:

```bibtex
@software{Maeurer2026TensorCategories,
  author    = {M{\"a}urer, Fabian},
  title     = {{TensorCategories.jl}},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.18760250},
  url       = {https://doi.org/10.5281/zenodo.18760250}
}
```

## Center of the Haagerup subfactor 

We computed the center of the Haagerup fusion category in [https://arxiv.org/abs/2601.20012](https://arxiv.org/abs/2601.20012) and stored it here.

```julia-repl
julia> using TensorCategories

# this is faster and what most people are probably more interested in
Z = numeric_unitary_center_H3()
Fusion Category with 12 simple objects

# Warning: this takes 30 min
julia> Z = haagerup_H3_center();
```

## License

The TensorCategoriesDatabase is licensed under the GNU General Public License v3.0 or later. 

Copyright (c) 2021 Fabian Mäurer and contributors. 

See [`LICENSE`](LICENSE) for the full license text.
See [`COPYRIGHT`](COPYRIGHT) for copyright information.

