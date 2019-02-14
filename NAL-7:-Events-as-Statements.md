------------------------- **Temporal deduction/explification** ----------------------------------

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
<br/>
<br/>
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

`//John is opening door_101`
<br/>
<br/>
`<John --> (/,open,_,door_101)>. :|: `
<br/>
<br/>
`6`
<br/>
<br/>
`//John is entering room_101`
<br/>
<br/>
`<John --> (/,enter,_,room_101)>. :|: `
<br/>
<br/>
`20`
<br/>
<br/>
`//If John enter room_101, he should open door_101 before`
<br/>
<br/>
`//outputMustContain('<<John --> (/,enter,_,room_101)> =\> (&/,<John --> (/,open,_,door_101)>,+6)>. :!6: %1.00;0.45%')`
<br/>
<br/>
`//new: variable introduction also in time:`
<br/>
<br/>
`//If someone enter room_101, he should open door_101 before`
<br/>
<br/>
`//outputMustContain('<< --> (/,enter,_,room_101)> =\> (&/,< --> (/,open,_,door_101)>,+6)>. :!6: %1.00;0.45%')`
<br/>
<br/>
`//adjusted +2 to +3 in both conditions`

----------------------------- **Induction on events** ------------------------

`//John is holding key_101 now`
<br/>
<br/>
`<(*,John,key_101) --> hold>. :|:  %1.00;0.90% `
<br/>
<br/>
`6`
<br/>
<br/>
`//irrelevant  'outputMustContain('<John --> (/,hold,_,key_101)>. :\: %1.00;0.90%') `
<br/>
<br/>
`//irrelevant  'outputMustContain('<key_101 --> (/,hold,John,_)>. :\: %1.00;0.90%') `
<br/>
<br/>
`//irrelevant  'outputMustContain('<John --> (/,hold,_,key_101)>. :\: %1.00;0.90%') `
<br/>
<br/>
`//irrelevant  'outputMustContain('<key_101 --> (/,hold,John,_)>. :\: %1.00;0.90%')`
<br/>
<br/>
`//If John open door_101, he will enter room_101`
<br/>
<br/>
`<<(*,John,door_101) --> open> =/> <(*,John,room_101) --> enter>>. :|:  %1.00;0.90% `
<br/>
<br/>
`20`
<br/>
<br/>
`//If John hold key_101 and open door_101 (after 6 steps), he will enter room_101`
<br/>
<br/>
`//outputMustContain('<(&/,<(*,John,key_101) --> hold>,+6,<(*,John,door_101) --> open>) =/> <(*,John,room_101) --> enter>>. :!6: %1.00;0.45%')`
<br/>
<br/>
`//changed from +2 to +4 due to changes in interval calculations`
<br/>
<br/>
`//this one is working, just throwing exception`

----------------------------- **Updating and revision** -----------------------------

`//John is holding key_101 now`
<br/>
<br/>
`<(*,John,key_101) --> hold>. :|: `
<br/>
<br/>
`6`
<br/>
<br/>
`//John is not holding key_101 now`
<br/>
<br/>
`<(*,John,key_101) --> hold>. :|: %0% `
<br/>
<br/>
`//Is John holding key_101 now? `
<br/>
<br/>
`<(*,John,key_101) --> hold>? :|: `
<br/>
<br/>
`200`
<br/>
<br/>
`//revision on events`
<br/>
<br/>
`//John maybe holding key_101 now`
<br/>
<br/>
`//outputMustContain('<John --> (/,hold,_,key_101)>. :!6: %0.50;0.95%')`
<br/>
<br/>
`//but also looking at it as separate:`
<br/>
<br/>
`//John will not hold key_101 in the future`
<br/>
<br/>
`//outputMustContain('<John --> (/,hold,_,key_101)>. :!6: %0.00;0.90%')`


------------------------------- **Temporal analogy** -------------------------------

`//If someone open door_101, he will enter room_101`
<br/>
<br/>
`<<(*, $x, door_101) --> open> =/> <(*, $x, room_101) --> enter>>. %0.95%`
<br/>
<br/>
`//If someone enter room_101, it means he leave corridor_100`
<br/>
<br/>
`<<(*, $x, room_101) --> enter> <|> <(*, $x, corridor_100) --> leave>>.`
<br/>
<br/>
`40`
<br/>
<br/>
`//If someone open door_101, he will leave corridor_100`
<br/>
<br/>
`//outputMustContain('<<(*,,door_101) --> open> =/> <(*,,corridor_100) --> leave>>. %0.95;0.81%')`

--------------------------------- **Inference on tense** -----------------------------

`//If someone hold key_101, he will enter room_101 (in 100 steps)`
<br/>
<br/>
`<(&/,<(*, $x, key_101) --> hold>,+100) =/> <(*, $x, room_101) --> enter>>.`
<br/>
<br/>
`//John held the key_101`
<br/>
<br/>
`<(*, John, key_101) --> hold>. :\:`
<br/>
<br/>
`210`
<br/>
<br/>
`//John will enter room_101`
<br/>
<br/>
`//outputMustContain('<(*,John,room_101) --> enter>. :!95: %1.00;0.81%')`
<br/>
<br/>
`//this one is working, but throws an exception`

------------------------------------ **Inference on tense** ---------------------------------

`//If someone hold key_101, he will enter room_101 (in 100 steps)`
<br/>
<br/>
`<(&/,<(*, $x, key_101) --> hold>,+100) =/> <(*, $x, room_101) --> enter>>.`
<br/>
<br/>
`//John is entering room_101 now`
<br/>
<br/>
`<(*,John,room_101) --> enter>. :|:`
<br/>
<br/>
`15`
<br/>
<br/>
`//John held the key_101 (105 steps before)`
<br/>
<br/>
`//outputMustContain('<(*,John,key_101) --> hold>. :!-105: %1.00;0.45%')`

------------------- **Inference on tense** -----------------

`//If John hold key_101, he will enter room_101`
<br/>
<br/>
`<<(*,John,key_101) --> hold> =/> <(*,John,room_101) --> enter>>. `
<br/>
<br/>
`//John is holding key_101 now`
<br/>
<br/>
`<(*,John,key_101) --> hold>. :|:`
<br/>
<br/> 
`20`
<br/>
<br/>
`//John will enter room_101`
<br/>
<br/>
`//outputMustContain('<(*,John,room_101) --> enter>. :!5: %1.00;0.81%')`

------------------- **Deduction with interval summation** -----------------

`//a + 1 = b`
<br/>
<br/>
`<(&/, a, +1) =/> b>.`
<br/>
<br/>
`//b + 1 = c`
<br/>
<br/>
`<(&/, b, +1) =/> c>.`
<br/>
<br/>
`10`
<br/>
<br/>
`//a + 2 = c`
<br/>
<br/>
`//outputMustContain('<(&/,a,+2) =/> c>. %1.00;0.81%')`