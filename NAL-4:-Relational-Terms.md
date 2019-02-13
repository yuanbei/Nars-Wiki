------------------------- **Structural Transformation** -------------------------------------

`//An acid and a base can have a reaction.`
<br/>
<br/>
`<(*,acid,base) --> reaction>.`
<br/>
<br/>
'2'
<br/>
<br/>
`//Acid can react with base.`
<br/>
<br/>
`outputMustContain('<acid --> (/,reaction,_,base)>. %1.00;0.90%')`
<br/>
<br/>
`//A base is something that has a reaction with an acid. `
<br/>
<br/>
`//outputMustContain('<base --> (/,reaction,acid,_)>. %1.00;0.90%')`

----------------------------- **Structural transformation** ---------------------------------

`//Acid can react with base.`
<br/>
<br/>
`<acid --> (/,reaction,_,base)>.`
<br/>
<br/>
'3'
<br/>
<br/>
`//An acid and a base can have a reaction.`
<br/>
<br/>
`outputMustContain('<(*,acid,base) --> reaction>. %1.00;0.90%')`
<br/>
<br/>
`//A base is something that has a reaction with an acid.`
<br/>
<br/>
`//outputMustContain('<base --> (/,reaction,acid,_)>. %1.00;0.90%')`

------------------------------ **Structural transformation** ----------------------------

`//A base is something that has a reaction with an acid.`
<br/>
<br/>
`<base --> (/,reaction,acid,_)>.`
<br/>
<br/>
`3`
<br/>
<br/>
`//Acid can react with base.`
<br/>
<br/>
`outputMustContain('<acid --> (/,reaction,_,base)>. %1.00;0.90%')`
<br/>
<br/>
`//An acid and a base can have a reaction.`
<br/>
<br/>
`//outputMustContain('<(*,acid,base) --> reaction>. %1.00;0.90%')`

------------------------------- **Structural transformation** -----------------------------

`//Neutralization is a relation between an acid and a base.`
<br/>
<br/>
`<neutralization --> (*,acid,base)>.`
<br/>
<br/>
`3`
<br/>
<br/>
`//Something that can neutralize a base is an acid.`
<br/>
<br/>
`//outputMustContain('<(\,neutralization,_,base) --> acid>. %1.00;0.90%')`
<br/>
<br/>
`//Something that can be neutralized by an acid is a base.`
<br/>
<br/>
`//outputMustContain('<(\,neutralization,acid,_) --> base>. %1.00;0.90%')`

------------------------------------------- **Structural transformation** -----------------------------------

`//Something that can neutralize a base is an acid.`
<br/>
<br/>
`<(\,neutralization,_,base) --> acid>.`
<br/>
<br/>
`2`
<br/>
<br/>
`//Neutralization is a relation between an acid and a base.`
<br/>
<br/>
`//outputMustContain('<neutralization --> (*,acid,base)>. %1.00;0.90%')`
<br/>
<br/>
`//Something that can be neutralized by an acid is a base.`
<br/>
<br/>
`//outputMustContain('<(\,neutralization,acid,_) --> base>. %1.00;0.90%')`

------------------------------------------- **Structural transformation** -----------------------------------------------

`//Something that can be neutralized by an acid is a base.`
<br/>
<br/>
`<(\,neutralization,acid,_) --> base>.`
<br/>
<br/>
`2`
<br/>
<br/>
`//Something that can neutralize a base is an acid.`
<br/>
<br/>
`//outputMustContain('<(\,neutralization,_,base) --> acid>. %1.00;0.90%')`
<br/>
<br/>
`//Neutralization is a relation between an acid and a base.`
<br/>
<br/>
`//outputMustContain('<neutralization --> (*,acid,base)>. %1.00;0.90%')`

--------------------------------- **Composition on both sides of a statement** ---------------------------

`//Bird is a type of animal.`
<br/>
<br/>
`<bird --> animal>.`
<br/>
<br/>
`//What is the relation between a bird and a plant?`
<br/>
<br/>
`<(*,bird,plant) --> ?x>?`
<br/>
<br/>
`6`
<br/>
<br/>
`//The relation between bird and plant is a type of relation between animal and plant.`
<br/>
<br/>
`//outputMustContain('<(*,bird,plant) --> (*,animal,plant)>. %1.00;0.81%')`

----------------------------- **Composition on both sides of a statement* ------------------------

`//Neutralization is a type of reaction.`
<br/>
<br/>
`<neutralization --> reaction>. `
<br/>
<br/>
`//What can be neutralized by acid?`
<br/>
<br/>
`<(\,neutralization,acid,_) --> ?x>?  `
<br/>
<br/>
`6`
<br/>
<br/>
`//What can be neutralized by acid can react with acid. `
<br/>
<br/>
`//outputMustContain('<(\,neutralization,acid,_) --> (\,reaction,acid,_)>. %1.00;0.81%')`

----------------------------- **Composition on both sides of a statement** -----------------------------

`//Soda is a type of base.`
<br/>
<br/>
`<soda --> base>.`
<br/>
<br/>
`//What is something that can neutralize a base?`
<br/>
<br/>
`<(/,neutralization,_,base) --> ?x>?`
<br/>
<br/>
`6`
<br/>
<br/>
`//What can neutraliz base can react with base.`
<br/>
<br/>
`//outputMustContain('<(/,neutralization,_,base) --> (/,neutralization,_,soda)>. %1.00;0.81%')`


------------------- **Compound composition, one premise** -----------------

`//Swan is a type of bird. `
<br/>
<br/>
`<swan --> bird>. %0.90% `
<br/>
<br/>
`//Is swimming swan a type of bird?`
<br/>
<br/>
`<(&,swan,swimmer) --> bird>?`
<br/>
<br/>
`32`
<br/>
<br/>
`//Swimming swan is a type of bird.`
<br/>
<br/>
`//outputMustContain('<(&,swan,swimmer) --> bird>. %0.90;0.73%')`

------------------- **Compound composition, one premise** -----------------

`//Swan is a type of bird.`
<br/>
<br/>
`<swan --> bird>. %0.90%`
<br/>
<br/>
`//Is swan a type of nonbird swimmer?`
<br/>
<br/>
`<swan --> (-,swimmer,bird)>?`
<br/>
<br/>
`32`
<br/>
<br/>
`//A swan is not a type of nonbird swimmer.`
<br/>
<br/>
`//outputMustContain('<swan --> (-,swimmer,bird)>. %0.10;0.73%')`

------------------- **Compound composition, one premise** -----------------

`//Swan is a type of bird.`
<br/>
<br/>
`<swan --> bird>. %0.90%`
<br/>
<br/>
`//Is being bird what differ swimmer from swan?`
<br/>
<br/>
`<(~,swimmer, swan) --> bird>? `
<br/>
<br/>
`32`
<br/>
<br/>
`//What differs swimmer from swan is not being bird.`
<br/>
<br/>
`//outputMustContain('<(~,swimmer,swan) --> bird>. %0.10;0.73%')`

------------------- **Compound composition, one premise** -----------------

`//Swan is a type of bird. `
<br/>
<br/>
`<swan --> bird>. %0.90%`
<br/>
<br/>
`//Is being bird what differ swimmer from swan?`
<br/>
<br/>
`<(~,swimmer, swan) --> bird>? `
<br/>
<br/>
`32`
<br/>
<br/>
`//What differs swimmer from swan is not being bird.`
<br/>
<br/>
`//outputMustContain('<(~,swimmer,swan) --> bird>. %0.10;0.73%')`

------------------- **Compound decomposition, one premise** -----------------

`//Robin is a type of swimming bird.`
<br/>
<br/>
`<robin --> (&,bird,swimmer)>. %0.90% `
<br/>
<br/>
`32`
<br/>
<br/>
`//Robin is a type of bird.`
<br/>
<br/>
`//outputMustContain('<robin --> bird>. %0.90;0.73%')`

------------------- **Compound decomposition, one premise** -----------------

`//Robin is a type of nonswimming bird.`
<br/>
<br/>
`<robin --> (-,bird,swimmer)>. %0.90%`
<br/>
<br/>
`32`
<br/>
<br/>
`//Robin is a type of bird.`
<br/>
<br/>
`//outputMustContain('<robin --> bird>. %0.90;0.73%')`

------------------- **Compound decomposition, one premise** -----------------

`//Boys and girls are youth.`
<br/>
<br/>
`<(|, boy, girl) --> youth>. %0.90%`
<br/>
<br/>
`32`
<br/>
<br/>
`//Boys are youth.`
<br/>
<br/>
`//outputMustContain('<boy --> youth>. %0.90;0.73%')`

------------------- **Compound decomposition, one premise** -----------------

`//What differs boys from gials are being strong.`
<br/>
<br/>
`<(~, boy, girl) --> [strong]>. %0.90%`
<br/>
<br/>
`32`
<br/>
<br/>
`//Boys are strong.`
<br/>
<br/>
`//outputMustContain('<boy --> [strong]>. %0.90;0.73%')`