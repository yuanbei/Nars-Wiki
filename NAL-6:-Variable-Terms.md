------------------------- **Compound composition, two premises** -------------------------------------

`//If robin can fly then robin is a type of bird.`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> bird>>.`
<br/>
<br/>
`//If robin can fly then robin may not a type of bird. `
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> bird>>. %0.00;0.60% `
<br/>
<br/>
`1`
<br/>
<br/>
`//If robin can fly then robin is a type of bird.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> ==> <robin --> bird>>. %0.86;0.91%')`

------------------------------------------- **Deduction** --------------------------------------

`//If robin is a type of bird then robin is a type of animal.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>.`
<br/>
<br/>
`//If robin can fly then robin is a type of bird.`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> bird>>.`
<br/>
<br/>
`14`
<br/>
<br/>
`//If robin can fly then robin is a type of animal.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> ==> <robin --> animal>>. %1.00;0.81%')`

--------------------------------------- **Exemplification** -------------------------------------

`//If robin can fly then robin is a type of bird.`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> bird>>.`
<br/>
<br/>
`//If robin is a type of bird then robin is a type of animal. `
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>.`
<br/>
<br/>
`19`
<br/>
<br/>
`//I guess if robin is a type of animal then robin can fly.`
<br/>
<br/>
`//outputMustContain('<<robin --> animal> ==> <robin --> [flying]>>. %1.00;0.45%')`

------------------------------- **Induction** -----------------------------

`//If robin is a type of bird then robin is a type of animal.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>. `
<br/>
<br/>
`//If robin is a type of bird then robin can fly.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> [flying]>>. %0.80%`
<br/>
<br/>
`140`
<br/>
<br/>
`//I guess if robin can fly then robin is a type of animal.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> ==> <robin --> animal>>. %1.00;0.39%')`
<br/>
<br/>
`//I guess if robin is a type of animal then robin can fly.`
<br/>
<br/>
`//outputMustContain('<<robin --> animal> ==> <robin --> [flying]>>. %0.80;0.45%')`

------------------------------------------- **Abduction** -----------------------------------

`//If robin is a type of bird then robin is a type of animal.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>.`
<br/>
<br/>
`//If robin can fly then robin is probably a type of animal.`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> animal>>. %0.8%`
<br/>
<br/>
`19`
<br/>
<br/>
`//I guess if robin is a type of bird then robin can fly.`
<br/>
<br/>
`//outputMustContain('<<robin --> bird> ==> <robin --> [flying]>>. %1.00;0.39%')`
<br/>
<br/>
`//I guess if robin can fly then robin is a type of bird.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> ==> <robin --> bird>>. %0.80;0.45%')`

------------------------------------------- **Detachment** -----------------------------------------------

`//If robin is a type of bird then robin can fly.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>. `
<br/>
<br/>
`//Robin is a type of bird. `
<br/>
<br/>
`<robin --> bird>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//Robin is a type of animal.`
<br/>
<br/>
`//outputMustContain('<robin --> animal>. %1.00;0.81%')`

--------------------------------- **Detachment** ---------------------------

`//Usually if robin is a type of bird then robin is a type of animal.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>. %0.70;0.90% `
<br/>
<br/>
`//Robin is a type of animal. `
<br/>
<br/>
`<robin --> animal>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//I guess robin is a type of bird.`
<br/>
<br/>
`//outputMustContain('<robin --> bird>. %1.00;0.36%')`

----------------------------- **Comparison** ------------------------

`//If robin is a type of bird then robin is a type of animal.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>.`
<br/>
<br/>
`//If robin is a type of bird then robin can fly.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> [flying]>>. %0.80%`
<br/>
<br/>
`14`
<br/>
<br/>
`//I guess robin is a type of animal if and only if robin can fly.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> <=> <robin --> animal>>. %0.80;0.45%')`

----------------------------- **Comparison** -----------------------------

`//If robin is a type of bird then usually robin is a type of animal.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>. %0.70%`
<br/>
<br/>
`//If robin can fly then robin is a type of animal. `
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> animal>>.  `
<br/>
<br/>
`19`
<br/>
<br/>
`//I guess robin is a type of bird if and only if robin can fly.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> <=> <robin --> bird>>. %0.70;0.45%')`


------------------------------- **Analogy** -------------------------------

`//If robin is a type of bird then robin is a type of animal.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>.`
<br/>
<br/>
`//Usually, robin is a type of bird if and only if robin can fly.`
<br/>
<br/>
`<<robin --> bird> <=> <robin --> [flying]>>. %0.80%`
<br/>
<br/>
`14`
<br/>
<br/>
`//If robin can fly then probably robin is a type of animal.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> ==> <robin --> animal>>. %0.80;0.65%')`

--------------------------------- **Analogy** -----------------------------

`//Robin is a type of bird.`
<br/>
<br/>
`<robin --> bird>.`
<br/>
<br/>
`//Usually, robin is a type of bird if and only if robin can fly.`
<br/>
<br/>
`<<robin --> bird> <=> <robin --> [flying]>>. %0.80% `
<br/>
<br/>
`1`
<br/>
<br/>
`//I guess usually robin can fly.`
<br/>
<br/>
`//outputMustContain('<robin --> [flying]>. %0.80;0.65%')`

------------------------------------ **Resemblance** ---------------------------------

`//Robin is a type of animal if and only if robin is a type of bird.`
<br/>
<br/>
`<<robin --> animal> <=> <robin --> bird>>. `
<br/>
<br/>
`//Robin is a type of bird if and only if robin can fly.`
<br/>
<br/>
`<<robin --> bird> <=> <robin --> [flying]>>. %0.9%`
<br/>
<br/>
`19`
<br/>
<br/>
`//Robin is a type of animal if and only if robin can fly.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> <=> <robin --> animal>>. %0.90;0.81%')`

------------------- **Conversions between Implication and Equivalence** -----------------

`//If robin can fly then robin is a type of bird.`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> bird>>. %0.9% `
<br/>
<br/>
`//If robin is a type of bird then robin can fly.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> [flying]>>. %0.9%`
<br/>
<br/>
`7`
<br/>
<br/>
`//Robin can fly if and only if robin is a type of bird.`
<br/>
<br/>
`//outputMustContain('<<robin --> [flying]> <=> <robin --> bird>>. %0.81;0.81%')`

------------------- **Compound composition, two premises** -----------------

`//If robin is a type of bird then robin is a type of animal. `
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>. `
<br/>
<br/>
`//If robin is a type of bird then robin can fly.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> [flying]>>. %0.9% `
<br/>
<br/>
`14`
<br/>
<br/>
`//If robin is a type of bird then usually robin is a type of animal and can fly.`
<br/>
<br/>
`//outputMustContain('<<robin --> bird> ==> (&&,<robin --> [flying]>,<robin --> animal>)>. %0.90;0.81%')`
<br/>
<br/>
`//If robin is a type of bird then robin is a type of animal or can fly.`
<br/>
<br/>
`//outputMustContain('<<robin --> bird> ==> (||,<robin --> [flying]>,<robin --> animal>)>. %1.00;0.81%')`

------------------- **Compound composition, two premises** -----------------

`//If robin is a type of bird then robin is a type of animal. `
<br/>
<br/>
`<<robin --> bird> ==> <robin --> animal>>. `
<br/>
<br/>
`//If robin can fly then robin is a type of animal.`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> animal>>. %0.9%`
<br/>
<br/>
`19`
<br/>
<br/>
`//If robin can fly and is a type of bird then robin is a type of animal.`
<br/>
<br/>
`//outputMustContain('<(&&,<robin --> [flying]>,<robin --> bird>) ==> <robin --> animal>>. %1.00;0.81%')`
<br/>
<br/>
`//If robin can fly or is a type of bird then robin is a type of animal.`
<br/>
<br/>
`//outputMustContain('<(||,<robin --> [flying]>,<robin --> bird>) ==> <robin --> animal>>. %0.90;0.81%')`

------------------- **Compound composition, two premises** -----------------

`//If robin is a type of bird then robin is not a type of flying animal.`
<br/>
<br/>
`<<robin --> bird> ==> (&&,<robin --> animal>,<robin --> [flying]>)>. %0%`
<br/>
<br/>
`//If robin is a type of bird then robin can fly.`
<br/>
<br/>
`<<robin --> bird> ==> <robin --> [flying]>>.`
<br/>
<br/>
`8`
<br/>
<br/>
`//It is unlikely that if a robin is a type of bird then robin is a type of animal.`
<br/>
<br/>
`//outputMustContain('<<robin --> bird> ==> <robin --> animal>>. %0.00;0.81%')`

------------------- **Compound composition, two premises** -----------------

`//Robin cannot be both a flyer and a swimmer.`
<br/>
<br/>
`(&&,<robin --> [flying]>,<robin --> swimmer>). %0%`
<br/>
<br/>
`//Robin can fly.`
<br/>
<br/>
`<robin --> [flying]>.`
<br/>
<br/>
`6`
<br/>
<br/>
`//Robin cannot swim.`
<br/>
<br/>
`//outputMustContain('<robin --> swimmer>. %0.00;0.81%')`

------------------- **Compound composition, two premises** -----------------

`//Robin can fly or swim.`
<br/>
<br/>
`(||,<robin --> [flying]>,<robin --> swimmer>).  `
<br/>
<br/>
`//Robin cannot swim.`
<br/>
<br/>
`<robin --> swimmer>. %0%` 
<br/>
<br/>
`2`
<br/>
<br/>
`//Robin can fly.`
<br/>
<br/>
`//outputMustContain('<robin --> [flying]>. %1.00;0.81%')`

------------------- **Compound composition, one premises** -----------------

`//Robin can fly.`
<br/>
<br/>
`<robin --> [flying]>. `
<br/>
<br/>
`//Can robin fly or swim?`
<br/>
<br/>
`(||,<robin --> [flying]>,<robin --> swimmer>)?` 
<br/>
<br/>
`7`
<br/>
<br/>
`//Robin can fly or swim.`
<br/>
<br/>
`//outputMustContain('(||,<robin --> [flying]>,<robin --> swimmer>). %1.00;0.81%')`

------------------- **Compound composition, one premises** -----------------

`//Robin can fly and swim.`
<br/>
<br/>
`(&&,<robin --> swimmer>,<robin --> [flying]>). %0.9%`
<br/>
<br/>
`//Robin can swim.`
<br/>
<br/>
`//outputMustContain('<robin --> swimmer>. %0.90;0.73%')` 
<br/>
<br/>
`5`
<br/>
<br/>
`//Robin can fly.`
<br/>
<br/>
`//outputMustContain('<robin --> [flying]>. %0.90;0.73%')`

-------------------------------------- **Negation** -------------------------------------

`//It is unlikely that robin cannot fly. `
<br/>
<br/>
`(--,<robin --> [flying]>). %0.1%`
<br/>
<br/>
`3`
<br/>
<br/>
`//Robin can fly.`
<br/>
<br/>
`//outputMustContain('<robin --> [flying]>. %0.90;0.90%')`

-------------------------------------- **Negation** -------------------------------------

`//Robin can fly. `
<br/>
<br/>
`<robin --> [flying]>. %0.9%`
<br/>
<br/>
`//Can robin fly or not?`
<br/>
<br/>
`(--,<robin --> [flying]>)?`
<br/>
<br/>
`30`
<br/>
<br/>
`//It is unlikely that robin cannot fly.`
<br/>
<br/>
`//outputMustContain('(--,<robin --> [flying]>). %0.10;0.90%')`

-------------------------------------- **Contraposition** -------------------------------------

`//It is unlikely that if robin is not a type of bird then robin can fly. `
<br/>
<br/>
`<(--,<robin --> bird>) ==> <robin --> [flying]>>. %0.1%`
<br/>
<br/>
`//If robin cannot fly then is robin a type of bird?`
<br/>
<br/>
`<(--,<robin --> [flying]>) ==> <robin --> bird>>?`
<br/>
<br/>
`29`
<br/>
<br/>
`//I guess it is unlikely that if robin cannot fly then robin is a type of bird.`
<br/>
<br/>
`//outputMustContain('<(--,<robin --> [flying]>) ==> <robin --> bird>>. %0.00;0.45%')`

-------------------------------------- **Conditional deduction** -------------------------------------

`//If robin can fly and has wings then robin is a bird.`
<br/>
<br/>
`<(&&,<robin --> [flying]>,<robin --> [with-wings]>) ==> <robin --> bird>>. `
<br/>
<br/>
`//robin can fly.`
<br/>
<br/>
`<robin --> [flying]>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//If robin has wings then robin is a bird`
<br/>
<br/>
`//outputMustContain('<<robin --> [with-wings]> ==> <robin --> bird>>. %1.00;0.81%')`

-------------------------------------- **Conditional deduction** -------------------------------------

`//If robin can fly, has wings, and chirps, then robin is a bird`
<br/>
<br/>
`<(&&,<robin --> [chirping]>,<robin --> [flying]>,<robin --> [with-wings]>) ==> <robin --> bird>>. `
<br/>
<br/>
`//robin can fly.`
<br/>
<br/>
`<<robin --> [flying]>. `
<br/>
<br/>
`5`
<br/>
<br/>
`//If robin has wings and chirps then robin is a bird.`
<br/>
<br/>
`//outputMustContain('<(&&,<robin --> [chirping]>,<robin --> [with-wings]>) ==> <robin --> bird>>. %1.00;0.81%')`

-------------------------------------- **Conditional deduction** -------------------------------------

`//If robin is a bird and it's living, then robin is an animal`
<br/>
<br/>
`<(&&,<robin --> bird>,<robin --> [living]>) ==> <robin --> animal>>.  `
<br/>
<br/>
`//If robin can fly, then robin is a bird`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> bird>>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//If robin is living and it can fly, then robin is an animal.`
<br/>
<br/>
`//outputMustContain('<(&&,<robin --> [flying]>,<robin --> [living]>) ==> <robin --> animal>>. %1.00;0.81%')`

-------------------------------------- **Conditional deduction** -------------------------------------

`//If robin can fly then robin is a bird.`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> bird>>.`
<br/>
<br/>
`//If robin both swims and flys then robin is a bird.`
<br/>
<br/>
`<(&&,<robin --> swimmer>,<robin --> [flying]>) ==> <robin --> bird>>.`
<br/>
<br/>
`7`
<br/>
<br/>
`//I guess robin swims.`
<br/>
<br/>
`//outputMustContain('<robin --> swimmer>. %1.00;0.45%')`

-------------------------------------- **Conditional deduction** -------------------------------------

`//If robin is has wings and chirps, then robin is a bird`
<br/>
<br/>
`<(&&,<robin --> [with-wings]>,<robin --> [chirping]>) ==> <robin --> bird>>. `
<br/>
<br/>
`//If robin can fly, has wings, and chirps, then robin is a bird`
<br/>
<br/>
`<(&&,<robin --> [flying]>,<robin --> [with-wings]>,<robin --> [chirping]>) ==> <robin --> bird>>.`
<br/>
<br/>
`5`
<br/>
<br/>
`//I guess that robin can fly.`
<br/>
<br/>
`//outputMustContain('<robin --> [flying]>. %1.00;0.45%')`

-------------------------------------- **Conditional deduction** -------------------------------------

`//If robin can fly and it has wings, then robin is living.`
<br/>
<br/>
`<(&&,<robin --> [flying]>,<robin --> [with-wings]>) ==> <robin --> [living]>>. %0.9%`
<br/>
<br/>
`//If robin can fly and robin is a bird then robin is living.`
<br/>
<br/>
`<(&&,<robin --> [flying]>,<robin --> bird>) ==> <robin --> [living]>>.`
<br/>
<br/>
`18`
<br/>
<br/>
`//I guess if robin is a bird, then robin has wings.`
<br/>
<br/>
`//outputMustContain('<<robin --> bird> ==> <robin --> [with-wings]>>. %1.00;0.42%')`
<br/>
<br/>
`//I guess if robin has wings, then robin is a bird.`
<br/>
<br/>
`//outputMustContain('<<robin --> [with-wings]> ==> <robin --> bird>>. %0.90;0.45%')`

-------------------------------------- **Conditional deduction** -------------------------------------

`//If robin can fly and robin chirps, then robin is a bird`
<br/>
<br/>
`<(&&,<robin --> [chirping]>,<robin --> [flying]>) ==> <robin --> bird>>. `
<br/>
<br/>
`//If robin can fly then usually robin has a beak.`
<br/>
<br/>
`<<robin --> [flying]> ==> <robin --> [with-beak]>>. %0.90%`
<br/>
<br/>
`18`
<br/>
<br/>
`//I guess that if robin chirps and robin has a beak, then robin is a bird.`
<br/>
<br/>
`//outputMustContain('<(&&,<robin --> [chirping]>,<robin --> [with-beak]>) ==> <robin --> bird>>. %1.00;0.42%')`