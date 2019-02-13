------------------------- **Compound composition, two premises** -------------------------------------

`//Swan is a type of swimmer.`
<br/>
<br/>
`<swan --> swimmer>. %0.90%`
<br/>
<br/>
`//Swan is a type of bird.`
<br/>
<br/>
`<swan --> bird>. %0.80%`
<br/>
<br/>
`16`
<br/>
<br/>
`//Swan is a type of bird or a type of swimmer.`
<br/>
<br/>
`//outputMustContain('<swan --> (|,bird,swimmer)>. %0.98;0.81%')`
<br/>
<br/>
`//Swan is a type of swimming bird. `
<br/>
<br/>
`//outputMustContain('<swan --> (&,bird,swimmer)>. %0.72;0.81%')`

----------------------------- **Compound composition, two premises** ---------------------------------

`//Sport is a type of competition. `
<br/>
<br/>
`<sport --> competition>. %0.90%`
<br/>
<br/>
`//Chess is a type of competition.`
<br/>
<br/>
`<chess --> competition>. %0.80% `
<br/>
<br/>
`16`
<br/>
<br/>
`//If something is either chess or sport, then it is a competition.`
<br/>
<br/>
`//outputMustContain('<(|,chess,sport) --> competition>. %0.72;0.81%')`
<br/>
<br/>
`//If something is both chess and sport, then it is a competition.`
<br/>
<br/>
`//outputMustContain('<(&,chess,sport) --> competition>. %0.98;0.81%')`

------------------------------ **Compound decomposition, two premises** ----------------------------

`//Robin is a type of bird or a type of swimmer. `
<br/>
<br/>
`<robin --> (|,bird,swimmer)>.`
<br/>
<br/>
`//Robin is not a type of swimmer. `
<br/>
<br/>
`<robin --> swimmer>. %0.00%`
<br/>
<br/>
`32`
<br/>
<br/>
`//Robin is a type of bird.`
<br/>
<br/>
`//outputMustContain('<robin --> bird>. %1.00;0.81%')`

------------------------------- **Compound decomposition, two premises** -----------------------------

`//Robin is not a type of swimmer.`
<br/>
<br/>
`<robin --> swimmer>. %0.00%`
<br/>
<br/>
`//Robin is not a nonswimming mammal.`
<br/>
<br/>
`<robin --> (-,mammal,swimmer)>. %0.00% `
<br/>
<br/>
`32`
<br/>
<br/>
`//Robin is not a type of mammal.`
<br/>
<br/>
`//outputMustContain('<robin --> mammal>. %0.00;0.81%')`

------------------------------------------- **Set operations** -----------------------------------

`//PlanetX is Mars, Pluto, or Venus.`
<br/>
<br/>
`<planetX --> {Mars,Pluto,Venus}>. %0.90% `
<br/>
<br/>
`//PlanetX is probably Pluto or Saturn.`
<br/>
<br/>
`<planetX --> {Pluto,Saturn}>. %0.70%`
<br/>
<br/>
`32`
<br/>
<br/>
`//PlanetX is Mars, Pluto, Saturn, or Venus.`
<br/>
<br/>
`//outputMustContain('<planetX --> {Mars,Pluto,Saturn,Venus}>. %0.97;0.81%')`
<br/>
<br/>
`//PlanetX is probably Pluto.`
<br/>
<br/>
`//outputMustContain('<planetX --> {Pluto}>. %0.63;0.81%')`

------------------------------------------- **Analogy-2** -----------------------------------------------

`//Gull is a type of swimmer. `
<br/>
<br/>
`<gull --> swimmer>. `
<br/>
<br/>
`//Gull is similar to a swan. `
<br/>
<br/>
`<gull <-> swan>.  `
<br/>
<br/>
`3`
<br/>
<br/>
`//I believe a swan is a type of swimmer. `
<br/>
<br/>
`//outputMustContain('<swan --> swimmer>. %1.00;0.81%')`

---------------------------------------- **"Resemblance** -------------------------------------------

`//Robin is similar to swan. `
<br/>
<br/>
`<robin <-> swan>. `
<br/>
<br/>
`//Gull is similar to swan. `
<br/>
<br/>
`<gull <-> swan>. `
<br/>
<br/>
`3`
<br/>
<br/>
`//Gull is similar to robin.`
<br/>
<br/>
`//outputMustContain('<gull <-> robin>. %1.00;0.81%')`

----------------------------- **Conversions between Inheritance and Similarity** ------------------------

`//Swan is a type of bird. `
<br/>
<br/>
`<swan --> bird>. `
<br/>
<br/>
`//Bird is not a type of swan. `
<br/>
<br/>
`<bird --> swan>. %0.10% `
<br/>
<br/>
`1`
<br/>
<br/>
`//Bird is different from swan.  `
<br/>
<br/>
`//outputMustContain('<bird <-> swan>.')`
<br/>
<br/>
`//outputMustContain('<bird <-> swan>. %0.10')`
<br/>
<br/>
`//outputMustContain('<bird <-> swan>. %0.10;0.81%')`

----------------------------- **Structure Transformation** -----------------------------

`//Bright is similar to smart. `
<br/>
<br/>
`<bright <-> smart>. %0.90% `
<br/>
<br/>
`//Is bright thing a type of smart thing?`
<br/>
<br/>
`<[smart] --> [bright]>?`
<br/>
<br/>
`6`
<br/>
<br/>
`//Bright thing is a type of smart thing. `
<br/>
<br/>
`//outputMustContain('<[bright] <-> [smart]>. %0.90;0.90%')`
<br/>
<br/>
`//outputMustContain('<[smart] --> [bright]>. %0.90;0.66%')`

------------------- **Conversions between Inheritance and Similarity** -----------------

`//Swan is a type of bird. `
<br/>
<br/>
`<swan --> bird>.`
<br/>
<br/>
`//Bird is different from swan.`
<br/>
<br/>
`<bird <-> swan>. %0.10% `
<br/>
<br/>
`1`
<br/>
<br/>
`//Bird is probably not a type of swan.  `
<br/>
<br/>
`//outputMustContain('<bird --> swan>. %0.10;0.73%')`

------------------- **Structure Transformation** -----------------

`//Birdie is similar to Tweety `
<br/>
<br/>
`<Birdie <-> Tweety>. %0.90%`
<br/>
<br/>
`//Is Birdie similar to Tweety?`
<br/>
<br/>
`<{Birdie} <-> {Tweety}>? `
<br/>
<br/>
`1`
<br/>
<br/>
`//Birdie is similar to Tweety.`
<br/>
<br/>
`//outputMustContain('<{Birdie} <-> {Tweety}>. %0.90;0.73%')`

------------------- **Conversions between inheritance and similarity** -----------------

`//Swan is a type of bird. `
<br/>
<br/>
`<swan --> bird>. %0.90%`
<br/>
<br/>
`//Is bird similar to swan?`
<br/>
<br/>
`<bird <-> swan>?`
<br/>
<br/>
`6`
<br/>
<br/>
`//I guess that bird is similar to swan. `
<br/>
<br/>
`//outputMustContain('<bird <-> swan>. %0.90;0.47%')`

------------------- **Conversions between inheritance and similarity** -----------------

`//A bird is similar to a swan. `
<br/>
<br/>
`<bird <-> swan>. %0.90% `
<br/>
<br/>
`//Is swan a type of bird?`
<br/>
<br/>
`<swan --> bird>?`
<br/>
<br/>
`6`
<br/>
<br/>
`//A swan is a type of bird.`
<br/>
<br/>
`//outputMustContain('<swan --> bird>. %0.90;0.81%')`

------------------- **Translating instance into inheritance** -----------------

`//Tweety is a bird.`
<br/>
<br/>
`<Tweety {-- bird>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//Tweety is an instance of bird.`
<br/>
<br/>
`//outputMustContain('<{Tweety} --> bird>. %1.00;0.90%')`

------------------- **Translating property into inheritance** -----------------

`//Ravens are black.`
<br/>
<br/>
`<raven --] black>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//Raven has a property black`
<br/>
<br/>
`//outputMustContain('<raven --> [black]>.')`