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
`//outputMustContain('<(&&,<$1 --> flyer>,<(*,$1,worms) --> food>) ==> < $1--> [with-wings]>>. %1.00;0.45%')`
<br/>
<br/>
`//I guess if something has wings, then it can fly and eats worms.`
<br/>
<br/>
`//outputMustContain('<<$1 --> [with-wings]> ==> (&&,<$1 --> flyer>,<(*,$1,worms) --> food>)>. %1.00;0.45%')`

--------------------------------- **Variable unification** ---------------------------

`If something is a bird, then it is an animal.`
<br/>
<br/>
`<<$x --> bird> ==> <$x --> animal>>.`
<br/>
<br/>
`A robin is a bird.`
<br/>
<br/>
`<robin --> bird>. `
<br/>
<br/>
`3`
<br/>
<br/>
`//A robin is an animal.`
<br/>
<br/>
`//outputMustContain('<robin --> animal>. %1.00;0.81%')`

----------------------------- **Variable elimination** ------------------------

`//If something is a bird, then it is an animal.`
<br/>
<br/>
`<<$x --> bird> ==> <$x --> animal>>. `
<br/>
<br/>
`//A tiger is an animal.`
<br/>
<br/>
`<tiger --> animal>. `
<br/>
<br/>
`10`
<br/>
<br/>
`//I guess that a tiger is a bird.`
<br/>
<br/>
`//outputMustContain('<tiger --> bird>. %1.00;0.45%')`

----------------------------- **Variable elimination** -----------------------------

`//Something is an animal if and only if it is a bird.`
<br/>
<br/>
`<<$x --> animal> <=> <$x --> bird>>. `
<br/>
<br/>
`//A robin is a bird.`
<br/>
<br/>
`<robin --> bird>.`
<br/>
<br/>
`3`
<br/>
<br/>
`//A robin is an animal.`
<br/>
<br/>
`//outputMustContain('<robin --> animal>. %1.00;0.81%')`

------------------------------- **Variable elimination** -------------------------------

`//Some bird can swim.`
<br/>
<br/>
`(&&,<#x --> bird>,<#x --> swimmer>). `
<br/>
<br/>
`//Swan is a type of bird.`
<br/>
<br/>
`<swan --> bird>. %0.90%`
<br/>
<br/>
`3`
<br/>
<br/>
`//I guess swan can swim.`
<br/>
<br/>
`//outputMustContain('<swan --> swimmer>. %0.90;0.43%')`

--------------------------------- **Variable elimination** -----------------------------

`//Tweety has wings.`
<br/>
<br/>
`<{Tweety} --> [with-wings]>.`
<br/>
<br/>
`//If something can chirp and has wings, then it is a bird.`
<br/>
<br/>
`<(&&,<$x --> [chirping]>,<$x --> [with-wings]>) ==> <$x --> bird>>.`
<br/>
<br/>
`23`
<br/>
<br/>
`//If Tweety can chirp, then it is a bird.`
<br/>
<br/>
`//outputMustContain('<<{Tweety} --> [chirping]> ==> <{Tweety} --> bird>>. %1.00;0.81%')`

------------------------------------ **Variable elimination** ---------------------------------

`//If something can fly, chirp, and eats worms, then it is a bird.`
<br/>
<br/>
`<(&&,<$x --> flyer>,<$x --> [chirping]>, <(*, $x, worms) --> food>) ==> <$x --> bird>>. `
<br/>
<br/>
`//Tweety can fly.`
<br/>
<br/>
`<{Tweety} --> flyer>.`
<br/>
<br/>
`7`
<br/>
<br/>
`//If Tweety can chirp and eats worms, then it is a bird.`
<br/>
<br/>
`//outputMustContain('<(&&,<(*,{Tweety},worms) --> food>,<{Tweety} --> [chirping]>) ==> <{Tweety} --> bird>>. %1.00;0.81%')`

------------------- **Multiple variable elimination** -----------------

`//Every lock can be opened by every key.`
<br/>
<br/>
`<(&&,<$x --> key>,<$y --> lock>) ==> <$y --> (/,open,$x,_)>>.  `
<br/>
<br/>
`//Lock-1 is a lock.`
<br/>
<br/>
`<{lock1} --> lock>. `
<br/>
<br/>
`20`
<br/>
<br/>
`//Lock-1 can be opened by every key.`
<br/>
<br/>
`//outputMustContain('<< $1--> key> ==> <{lock1} --> (/,open,,_)>>. %1.00;0.81%')`

------------------- **Multiple variable elimination** -----------------

`//Every lock can be opened by some key.`
<br/>
<br/>
`<<$x --> lock> ==> (&&,<#y --> key>,<$x --> (/,open,#y,_)>)>.  `
<br/>
<br/>
`//Lock-1 is a lock.`
<br/>
<br/>
`<{lock1} --> lock>. `
<br/>
<br/>
`9`
<br/>
<br/>
`//Some key can open Lock-1.`
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> key>,<{lock1} --> (/,open,#1,_)>). %1.00;0.81%')`

------------------- **Multiple variable elimination** -----------------

`//There is a lock that can be opened by every key.`
<br/>
<br/>
`(&&,<#x --> lock>,<<$y --> key> ==> <#x --> (/,open,$y,_)>>).  `
<br/>
<br/>
`//Lock-1 is a lock.`
<br/>
<br/>
`<{lock1} --> lock>.`
<br/>
<br/>
`9`
<br/>
<br/>
`//I guess Lock-1 can be opened by every key.`
<br/>
<br/>
`//outputMustContain('<< $1--> key> ==> <{lock1} --> (/,open,,_)>>. %1.00;0.43%')`

------------------- **Multiple variable elimination** -----------------

`//There is a key that can open some lock.`
<br/>
<br/>
`(&&,<#x --> (/,open,#y,_)>,<#x --> lock>,<#y --> key>).  `
<br/>
<br/>
`//Lock-1 is a lock.`
<br/>
<br/>
`<{lock1} --> lock>.`
<br/>
<br/>
`18`
<br/>
<br/>
`//I guess there is a key that can open Lock-1.`
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> key>,<{lock1} --> (/,open,#1,_)>). %1.00;0.43%')`

------------------- **Variable introduction** -----------------

`//A swan is a bird.`
<br/>
<br/>
`<swan --> bird>.  `
<br/>
<br/>
`//A swan is usually a swimmer.`
<br/>
<br/>
`<swan --> swimmer>. %0.80%`
<br/>
<br/>
`3`
<br/>
<br/>
`//I guess a bird is usually a swimmer.`
<br/>
<br/>
`//outputMustContain('<< $1--> bird> ==> <$1 --> swimmer>>. %0.80;0.45%')`
<br/>
<br/>
`//I guess a swimmer is a bird.`
<br/>
<br/>
`//outputMustContain('<<$1 --> swimmer> ==> <$1 --> bird>>. %1.00;0.39%')`
<br/>
<br/>
`//I guess a bird is usually a swimmer, and the other way around.`
<br/>
<br/>
`//outputMustContain('<< $1--> bird> <=> < $1--> swimmer>>. %0.80;0.45%')`
<br/>
<br/>
`//Some bird can swim.`
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> bird>,<#1 --> swimmer>). %0.80;0.81%')`

------------------- **Variable introduction** -----------------

`//A gull is a swimmer.`
<br/>
<br/>
`<gull --> swimmer>. `
<br/>
<br/>
`//Usually, a swan is a swimmer.`
<br/>
<br/>
`<swan --> swimmer>. %0.80% `
<br/>
<br/>
`3`
<br/>
<br/>
`//I guess what can be said about gull usually can also be said about swan.`
<br/>
<br/>
`//outputMustContain('<<gull --> $1> ==> <swan -->$1 >>. %0.80;0.45%')`
<br/>
<br/>
`//I guess what can be said about swan can also be said about gull.`
<br/>
<br/>
`//outputMustContain('<<swan -->$1 > ==> <gull --> $1>>. %1.00;0.39%')`
<br/>
<br/>
`//I guess gull and swan share most properties.`
<br/>
<br/>
`//outputMustContain('<<gull -->$1 > <=> <swan --> $1>>. %0.80;0.45%')`
<br/>
<br/>
`//Gull and swan have some common property.`
<br/>
<br/>
`//outputMustContain('(&&,<gull --> #1>,<swan --> #1>). %0.80;0.81%')`

------------------- **Variables introduction** -----------------

`//Key-1 opens Lock-1.`
<br/>
<br/>
`<{key1} --> (/,open,_,{lock1})>. `
<br/>
<br/>
`//Key-1 is a key.`
<br/>
<br/>
`<{key1} --> key>.`
<br/>
<br/>
`45`
<br/>
<br/>
`//I guess every key can open Lock-1.`
<br/>
<br/>
`//outputMustContain('<< --> key> ==> < --> (/,open,_,{lock1})>>. %1.00;0.45%')`
<br/>
<br/>
`//Some key can open Lock-1.`
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> (/,open,_,{lock1})>,<#1 --> key>). %1.00;0.81%')`
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> (/,open,_,{lock1})>,<#1 --> key>). %1.00;0.25%')`

------------------- **Multiple variables introduction** -----------------

`//Lock-1 can be opened by every key.`
<br/>
<br/>
`<<$x --> key> ==> <{lock1} --> (/,open,$x,_)>>. `
<br/>
<br/>
`//Lock-1 is a lock.`
<br/>
<br/>
`<{lock1} --> lock>. `
<br/>
<br/>
`166`
<br/>
<br/>
`//There is a lock that can be opened by every key.`
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> lock>,<< --> key> ==> <#1 --> (/,open,,_)>>). %1.00;0.81%')`
<br/>
<br/>
`//I guess every lock can be opened by every key.`
<br/>
<br/>
`//outputMustContain('<(&&,< $1--> key>,< $1--> lock>) ==> <$1 --> (/,open,,_)>>. %1.00;0.45%')`

----------------------------- **Multiple variables introduction** -------------------------

`//Lock-1 can be opened by some key.`
<br/>
<br/>
`(&&,<#x --> key>,<{lock1} --> (/,open,#x,_)>).  `
<br/>
<br/>
`//Lock-1 is a lock.`
<br/>
<br/>
`<{lock1} --> lock>. `
<br/>
<br/>
`17`
<br/>
<br/>
`//There is a key that can open some lock.`
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> key>,<#2 --> (/,open,#1,_)>,<#2 --> lock>). %1.00;0.81%')`
<br/>
<br/>
``//I guess every lock can be opened by some key.``
<br/>
<br/>
``//outputMustContain('<< --> lock> ==> (&&,<#2 --> key>,< --> (/,open,#2,_)>)>. %1.00;0.45%')``

-------------------------------------- **Recursion** -------------------------------------

`//0 is a number`
<br/>
<br/>
`<0 --> num>. %1.00;0.90%`
<br/>
<br/>
`//If n is a number, n+1 is also a number`
<br/>
<br/>
`<< $1--> num> ==> <(*,) --> num>>. %1.00;0.90%`
<br/>
<br/>
`//3 is a number?`
<br/>
<br/>
`<(*,(*,(*,0))) --> num>?`
<br/>
<br/>
`70000`
<br/>
<br/>
`//I guess 3 is a number`
<br/>
<br/>
`//outputMustContain('<(*,(*,(*,0))) --> num>. %1.00;0.66%')  `

------------------------ **Second level variable unification** ------------------------

`//there is a lock which is opened by all keys`
<br/>
<br/>
`(&&,<#1 --> lock>,<<$1 --> key> ==> <#1 --> (/,open,,_)>>). %1.00;0.90% `
<br/>
<br/>
`//key1 is a key`
<br/>
<br/>
`<{key1} --> key>. %1.00;0.90% `
<br/>
<br/>
`5`
<br/>
<br/>
`//there is a lock which is opened by key1`
<br/>
<br/>
`//outputMustContain('(&&,<#1 --> (/,open,{key1},_)>,<#1 --> lock>). %1.00;0.81%')`

------------------------ **Second level variable unification** ----------------------------

`//all locks are opened by some key`
<br/>
<br/>
`<<$1 --> lock> ==> (&&,<#2 --> key>,< --> (/,open,#2,_)>)>. %1.00;0.90% `
<br/>
<br/>
`//key1 is a key`
<br/>
<br/>
`<{key1} --> key>. %1.00;0.90% `
<br/>
<br/>
`5`
<br/>
<br/>
`//maybe all locks are opened by key1`
<br/>
<br/>
`//outputMustContain('<< $1--> lock> ==> <$1 --> (/,open,{key1},_)>>. %1.00;0.43%')`

------------------- **Second variable introduction (induction)** ---------------------

`//If something opens lock1, it is a key`
<br/>
<br/>
`<<lock1 --> (/,open,$1,_)> ==> < --> key>>.`
<br/>
<br/>
`//lock1 is a key`
`<lock1 --> lock>.`

`7`

`//there is a lock with the property that when opened by something, this something is a key (induction)`
`//outputMustContain('<(&&,<#1 --> (/,open,,_)>,<#1 --> lock>) ==> < --> key>>. %1.00;0.45%')`

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