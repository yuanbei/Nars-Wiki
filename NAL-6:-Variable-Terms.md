------------------------- **Variable unification** -------------------------------------

`//If something is a bird, then it is a flyer.`
<br/>
<br/>
`<<$x --> bird> ==> <$x --> flyer>>.`
<br/>
<br/>
`//If something is a bird, then it is not a flyer. `
<br/>
<br/>
`<<$y --> bird> ==> <$y --> flyer>>. %0.00;0.70% `
<br/>
<br/>
`1`
<br/>
<br/>
`//If something is a bird, then usually, it is a flyer. `
<br/>
<br/>
`outputMustContain('<< $1--> bird> ==> < $1--> flyer>>. %0.79;0.92%')`

---------------------------------- **Variable unification** --------------------------------

`//If something is a bird, then it is an animal. `
<br/>
<br/>
`<<$x --> bird> ==> <$x --> animal>>. `
<br/>
<br/>
`//If something is a robin, then it is a bird. `
<br/>
<br/>
`<<$y --> robin> ==> <$y --> bird>>. `
<br/>
<br/>
`3`
<br/>
<br/>
`//If something is a robin, then it is an animal. `
<br/>
<br/>
`//outputMustContain('<< $1--> robin> ==> < $1--> animal>>. %1.00;0.81%')`
<br/>
<br/>
`//I guess that if something is an animal, then it is a robin. `
<br/>
<br/>
`//outputMustContain('<< $1--> animal> ==> < $1--> robin>>. %1.00;0.45%')`

---------------------------------- **Variable unification** --------------------------------

`//If something is a swan, then it is a bird.`
<br/>
<br/>
`<<$x --> swan> ==> <$x --> bird>>. %1.00;0.80%  `
<br/>
<br/>
`//If something is a swan, then it is a swimmer.`
<br/>
<br/>
`<<$y --> swan> ==> <$y --> swimmer>>. %0.80% `
<br/>
<br/>
`3`
<br/>
<br/>
`//I believe that if something is a swan, then it is a bird or a swimmer.`
<br/>
<br/>
`//outputMustContain('<< $1--> swan> ==> (||,< $1--> bird>,< $1--> swimmer>)>. %1.00;0.72%')`
<br/>
<br/>
`//I believe that if something is a swan, then usually, it is both a bird and a swimmer.`
<br/>
<br/>
`//outputMustContain('<< $1 --> swan> ==> (&&,< $1 --> bird>,< $1--> swimmer>)>. %0.80;0.72%')`

------------------------------- **Variable unification** -----------------------------

`//What can be said about bird can also be said about robin.`
<br/>
<br/>
`<<bird --> $x> ==> <robin --> $x>>.`
<br/>
<br/>
`//What can be said about swimmer usually can also be said about robin.`
<br/>
<br/>
`<<swimmer --> $y> ==> <robin --> $y>>. %0.70;0.90%  `
<br/>
<br/>
`3`
<br/>
<br/>
`//What can be said about bird and swimmer can also be said about robin.`
<br/>
<br/>
`outputMustContain('<(&&,<bird --> $1>,<swimmer --> $1>) ==> <robin --> >>. %1.00;0.81%')`
<br/>
<br/>
`//What can be said about bird or swimmer can also be said about robin.`
<br/>
<br/>
`//outputMustContain('<(||,<bird -->$1 >,<swimmer --> $1>) ==> <robin --> >>. %0.70;0.81%')`

------------------------------ **Variable unification** ------------------------------

`//If something can fly and chirp, then it is a bird.`
<br/>
<br/>
`<(&&,<$x --> flyer>,<$x --> [chirping]>) ==> <$x --> bird>>. `
<br/>
<br/>
`//If something has wings, then it can fly.`
<br/>
<br/>
`<<$y --> [with-wings]> ==> <$y --> flyer>>. `
<br/>
<br/>
`8`
<br/>
<br/>
`//If something can chirp and has wings, then it is a bird.`
<br/>
<br/>
`//outputMustContain('<(&&,<$1 --> [chirping]>,<$1 --> [with-wings]>) ==> <$1 --> bird>>. %1.00;0.81%')`

---------------------------------- **Variable unification** --------------------------------

`//If something can fly, chirp, and eats worms, then it is a bird.`
<br/>
<br/>
`<(&&,<$x --> flyer>,<$x --> [chirping]>, <(*, $x, worms) --> food>) ==> <$x --> bird>>. `
<br/>
<br/>
`//If something can chirp and has wings, then it is a bird.`
<br/>
<br/>
`<(&&,<$x --> [chirping]>,<$x --> [with-wings]>) ==> <$x --> bird>>.`
<br/>
<br/>
`12`
<br/>
<br/>
`//If something can fly and eats worms, then I guess it has wings.`
<br/>
<br/>
`//outputMustContain('<(&&,< --> flyer>,<(*,,worms) --> food>) ==> < --> [with-wings]>>. %1.00;0.45%')`
<br/>
<br/>
`//I guess if something has wings, then it can fly and eats worms.`
<br/>
<br/>
`//outputMustContain('<< --> [with-wings]> ==> (&&,< --> flyer>,<(*,,worms) --> food>)>. %1.00;0.45%')`

--------------------------------- **Variable unification** ---------------------------

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