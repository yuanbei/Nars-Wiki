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

//---------------------------------------- **"Resemblance** -------------------------------------------

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
