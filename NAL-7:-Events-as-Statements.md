------------------------- **Temporal deduction/explification** -------------------------------------

`//Someone enter the room_101 after he open the door_101`
<br/>
<br/>
`<<(*, $x, room_101) --> enter> =\> <(*, $x, door_101) --> open>>. %0.9% `
<br/>
<br/>
`//Someone open the door_101 after he hold the key_101`
<br/>
<br/>
`<<(*, $y, door_101) --> open> =\> <(*, $y, key_101) --> hold>>. %0.8% `
<br/>
<br/>
`100`
<br/>
<br/>
`//If someone enter room_101, he should hold key_101 before`
<br/>
<br/>
`//outputMustContain('<<(*,$1,room_101) --> enter> =\> <(*,$1,key_101) --> hold>>.`
<br/>
<br/>
`//If someone hold key_101, he will enter room_101`
<br/>
<br/>
`//outputMustContain('<<(*,$1,key_101) --> hold> =/> <(*,$1,room_101) --> enter>>.`

------------------------------- **Temporal induction/comparison** -----------------------------

`//Someone open door_101 before he enter room_101`
<br/>
<br/>
`<<(*, $x, door_101) --> open> =/> <(*, $x, room_101) --> enter>>. %0.9%  `
<br/>
<br/>
`//Someone open door_101 after he hold key_101`
`<<(*, $y, door_101) --> open> =\> <(*, $y, key_101) --> hold>>. %0.8% `
<br/>
<br/>
`100`
<br/>
<br/>
`//If someone hold key_101, he will enter room_101`
<br/>
<br/>
`//outputMustContain('<<(*,,key_101) --> hold> =/> <(*,,room_101) --> enter>>. %0.90;0.39%')  `
<br/>
<br/>
`//If someone enter room_101, he should hold key_101 before`
<br/>
<br/>
`//outputMustContain('<<(*,,room_101) --> enter> =\> <(*,,key_101) --> hold>>. %0.80;0.42%') `
<br/>
<br/>
`//If someone hold key_101, it means he will enter room_101`
<br/>
<br/>
`//outputMustContain('<<(*,,key_101) --> hold> </> <(*,,room_101) --> enter>>. %0.73;0.44%')`

--------------------------------------- **Inference on tense** -------------------------------------

`//John hold key_101 before he enter room_101`
<br/>
<br/>
`<<(*,John,key_101) --> hold> =/> <(*,John,room_101) --> enter>>. `
<br/>
<br/>
`//John is holding key_101 now`
`<(*,John,key_101) --> hold>. :|:`
<br/>
<br/>
`20`
<br/>
<br/>
`//John will enter the room_101`
<br/>
<br/>
`//outputMustContain('<(*,John,room_101) --> enter>. :!5: %1.00;0.81%')`

------------------------------- **Inference on tense** -----------------------------

`//John hold key_101 before he enter room_101`
<br/>
<br/>
`<<(*,John,key_101) --> hold> =/> <(*,John,room_101) --> enter>>. %1.00;0.90%`
 <br/>
<br/>
`//John entered room_101`
<br/>
<br/>
`<(*,John,room_101) --> enter>. :\: %1.00;0.90%  `
<br/>
<br/>
`3`
<br/>
<br/>
`//outputMustContain('<(*,John,key_101) --> hold>. :!-10: %1.00;0.45%')`

------------------------------------------- **Inference on tense** -----------------------------------

`//John is opening door_101 now`
<br/>
<br/>
`<(*,John,door_101) --> open>. :|: `
<br/>
<br/>
`6`
<br/>
<br/>
`//John is entering room_101 now`
<br/>
<br/>
`<(*,John,room_101) --> enter>. :|: `
<br/>
<br/>
`10`
<br/>
<br/>
`//John will enter room_101 after he open door_101`
<br/>
<br/>
`//outputMustContain('<<(*,John,room_101) --> enter> =\> (&/,<(*,John,door_101) --> open>,+6)>. :!6: %1.00;0.45%')`

-------------------------------- **Induction on events ** -------------------------------------

`//John is opening door_101 now`
<br/>
<br/>
`<(*,John,door_101) --> open>. :|: `
<br/>
<br/>
`11`
<br/>
<br/>
`//John is not entering room_101 now`
<br/>
<br/>
`<(*,John,room_101) --> enter>. :|: %0% `
<br/>
<br/>
`10`
<br/>
<br/>
`//If John open the door_101, he will not enter room_101`
<br/>
<br/>
`//outputMustContain('<(&/,<(*,John,door_101) --> open>,+11) =/> <(*,John,room_101) --> enter>>. :!11: %0.00;0.45%')`
<br/>
<br/>
`//If John enter the door_101, it doesn't mean he will enter the room_101`
<br/>
<br/>
`//outputMustContain('<(&/,<(*,John,door_101) --> open>,+11) </> <(*,John,room_101) --> enter>>. :!11: %0.00;0.45%')`
<br/>
<br/>
`//adjusted +3 to +4`
<br/>
<br/>
`//original output (1.3.3): `
<br/>
<br/>
`//OUT: <<(*,John,room_101) --> enter>=\><(*,John,door_101) --> open>>. :\: %1.00;0.45%  `
<br/>
<br/>
`//OUT: <<(*,John,door_101) --> open>=/><(*,John,room_101) --> enter>>. :\: %1.00;0.45%   `
<br/>
<br/>
`//OUT: <<(*,John,door_101) --> open></><(*,John,room_101) --> enter>>. :\: %1.00;0.45%   `
<br/>
<br/>
`//OUT: <<(*,John,room_101) --> enter>=\><(*,John,door_101) --> open>>. %1.00;0.45%   `
<br/>
<br/>
`//OUT: <<(*,John,door_101) --> open>=/><(*,John,room_101) --> enter>>. %1.00;0.45%   `
<br/>
<br/>
`//OUT: <<(*,John,door_101) --> open></><(*,John,room_101) --> enter>>. %1.00;0.45%   `
<br/>
<br/>

--------------------------------- **Induction on events** ---------------------------

//John is opening door_101
<John --> (/,open,_,door_101)>. :|: 

6

//John is entering room_101
<John --> (/,enter,_,room_101)>. :|: 

20

//If John enter room_101, he should open door_101 before
//outputMustContain('<<John --> (/,enter,_,room_101)> =\> (&/,<John --> (/,open,_,door_101)>,+6)>. :!6: %1.00;0.45%')

//new: variable introduction also in time:

//If someone enter room_101, he should open door_101 before
//outputMustContain('<<$1 --> (/,enter,_,room_101)> =\> (&/,<$1 --> (/,open,_,door_101)>,+6)>. :!6: %1.00;0.45%')

//adjusted +2 to +3 in both conditions

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