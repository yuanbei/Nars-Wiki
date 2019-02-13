---------------------------------------------- **Revision** ----------------------------------------------------

`// Robin is similar to swan.`
<br/>
<br/>
`<robin <-> swan>.  `
<br/>
<br/>
`// I think robin is not similar to swan.`
<br/>
<br/>
`<robin <-> swan>. %0.10;0.60% `
<br/>
<br/>
`1`
<br/>
<br/>
`// Robin is probably similar to swan. `
<br/>
<br/>
`// outputMustContain('<robin <-> swan>. %0.87;0.91%')`

---------------------------------------------- **Comparison** -------------------------------------------------

`//Swan is a type of swimmer.`
<br/>
<br/>
`<swan --> swimmer>. %0.90% `
<br/>
<br/>
`//Swan is a type of bird. `
<br/>
<br/>
`<swan --> bird>.  `
<br/>
<br/>
`3`
<br/>
<br/>
`//I guess that bird is similar to swimmer.`
<br/>
<br/>
`//outputMustContain('<bird <-> swimmer>. %0.90;0.45%')`

---------------------------------------------- **Backward Inference** -----------------------------------------

`//Bird is a type of swimmer.`
<br/>
<br/>
`<bird --> swimmer>.  `
<br/>
<br/>
`//What is a swimmer?`
<br/>
<br/>
`<{?1} --> swimmer>?   `
<br/>
<br/>
`5`
<br/>
<br/>
`//What is a bird?`
<br/>
<br/>
`//outputMustContain('<{?1} --> bird>?')`

---------------------------------------------- **Comparison-2** ---------------------------------------------

`//Sport is a type of competition. `
<br/>
<br/>
`<sport --> competition>. `
<br/>
<br/>
`//Chess is a type of competition. `
<br/>
<br/>
`<chess --> competition>. %0.90% `
<br/>
<br/>
`3`
<br/>
<br/>
`//I guess chess is similar to sport.`
<br/>
<br/>
`//outputMustContain('<chess <-> sport>. %0.90;0.45%')`

------------------------------------------- **Analogy** -----------------------------------------------

`//Swan is a type of swimmer. `
<br/>
<br/>
`<swan --> swimmer>. `
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
`//I think gull is a type of swimmer.`
<br/>
<br/>
`//outputMustContain('<gull --> swimmer>. %1.00;0.81%')`

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

------------------- **Translating instance-property into inheritance** -----------------

`//Tweety is yellow.`
<br/>
<br/>
`<Tweety {-] yellow>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//The instance Tweety has a property yellow`
<br/>
<br/>
`//outputMustContain('<{Tweety} --> [yellow]>.')`

------------------- **Set definition** -----------------

`//Tweety is Birdie.`
<br/>
<br/>
`<{Tweety} --> {Birdie}>. `
<br/>
<br/>
`3`
<br/>
<br/>
`//Birdie is similar to Tweety. `
<br/>
<br/>
`//outputMustContain('<{Birdie} <-> {Tweety}>. %1.00;0.90%')`

------------------- **Set definition** -----------------

`//Smart thing is a type of bright thing.`
<br/>
<br/>
`<[smart] --> [bright]>. `
<br/>
<br/>
`1`
<br/>
<br/>
`//Bright thing is similar to smart thing.`
<br/>
<br/>
`//outputMustContain('<[bright] <-> [smart]>. %1.00;0.90%')`

------------------- **Set definition** -----------------

`//Birdie is similar to Tweety. `
<br/>
<br/>
`<{Birdie} <-> {Tweety}>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//Birdie is similar to Tweety.`
<br/>
<br/>
`//outputMustContain('<Birdie <-> Tweety>. %1.00;0.90%')`
<br/>
<br/>
`//Tweety is Birdie.`
<br/>
<br/>
`//outputMustContain('<{Tweety} --> {Birdie}>. %1.00;0.90%')`

------------------- **Set definition** -----------------

`//Bright thing is similar to smart thing.`
<br/>
<br/>
`<[bright] <-> [smart]>.`
<br/>
<br/>
`1`
<br/>
<br/>
`//Bright is similar to smart.`
<br/>
<br/>
`//outputMustContain('<bright <-> smart>. %1.00;0.90%')`
<br/>
<br/>
`//Bright thing is a type of smart thing.`
<br/>
<br/>
`//outputMustContain('<[bright] --> [smart]>. %1.00;0.90%')`