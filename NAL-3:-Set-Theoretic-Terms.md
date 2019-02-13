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

------------------------------------------- **Set operations** -----------------------------------------------

`//PlanetX is Mars, Pluto, or Venus.`
<br/>
<br/>
`<planetX --> {Mars,Pluto,Venus}>. %0.90% `
<br/>
<br/>
`//PlanetX is probably neither Pluto nor Saturn.`
<br/>
<br/>
`<planetX --> {Pluto,Saturn}>. %0.10%`
<br/>
<br/>
`32`
<br/>
<br/>
`//PlanetX is Mars, Pluto, Saturn, or Venus.`
<br/>
<br/>
`//outputMustContain('<planetX --> {Mars,Pluto,Saturn,Venus}>. %0.91;0.81%')`
<br/>
<br/>
`//PlanetX is either Mars or Venus.`
<br/>
<br/>
`//outputMustContain('<planetX --> {Mars,Venus}>. %0.81;0.81%')`

--------------------------------- **Composition on both sides of a statement** ---------------------------

`//Bird is a type of animal. `
<br/>
<br/>
`<bird --> animal>. %0.90% `
<br/>
<br/>
`//Is a swimming bird a type of swimming animal?`
<br/>
<br/>
`<(&,bird,swimmer) --> (&,animal,swimmer)>?`
<br/>
<br/>
`32`
<br/>
<br/>
`//A swimming bird is probably a type of swimming animal.`
<br/>
<br/>
`//outputMustContain('<(&,bird,swimmer) --> (&,animal,swimmer)>. %0.90;0.73%')`

----------------------------- **Composition on both sides of a statement** ------------------------

`//Bird is a type of animal.`
<br/>
<br/>
`<bird --> animal>. %0.90%`
<br/>
<br/>
`//Is a nonanimal swimmer a type of a nonbird swimmer?`
<br/>
<br/>
`<(-,swimmer,animal) --> (-,swimmer,bird)>?   `
<br/>
<br/>
`32`
<br/>
<br/>
`//A nonanimal swimmer is probably a type of nonbird swimmer.`
<br/>
<br/>
`//outputMustContain('<(-,swimmer,animal) --> (-,swimmer,bird)>. %0.90;0.73%')`

----------------------------- **Compound composition, one premise** -----------------------------

`//Swan is a type of bird. `
<br/>
<br/>
`<swan --> bird>. %0.90%`
<br/>
<br/>
`//Is a swan a type of bird or swimmer?`
<br/>
<br/>
`<swan --> (|,bird,swimmer)>?`
<br/>
<br/>
`32`
<br/>
<br/>
`//A swan is probably a type of bird or swimmer.`
<br/>
<br/>
`//outputMustContain('<swan --> (|,bird,swimmer)>. %0.90;0.73%')`


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
