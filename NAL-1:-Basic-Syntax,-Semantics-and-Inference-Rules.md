---------------------------------------------- **Revision** ----------------------------------------------------``

```
// Bird is a type of swimmer.
<br/>
<br/>
<bird --> swimmer>.
<br/>
<br/>
// Bird is probably not a type of swimmer.
<br/>
<br/>
<bird --> swimmer>. %0.10;0.60%
<br/>
<br/>
1
<br/>
<br/>
// Bird is very likely to be a type of swimmer.
<br/>
<br/>
// outputMustContain('<bird --> swimmer>. %0.87;0.91%')

```

---------------------------------------------- **Deduction** ---------------------------------------------------

`// Bird is a type of animal.`
<br/>
<br/>
`<bird --> animal>.`
<br/>
<br/>
`// Robin is a type of bird.`
<br/>
<br/>
`<robin --> bird>.`
<br/>
<br/>
`3`
<br/>
<br/>
`// Robin is a type of animal.`
<br/>
<br/>
`// outputMustContain('<robin --> animal>. %1.00;0.81%')`

---------------------------------------------- **Induction** ---------------------------------------------------

`// Swan is a type of swimmer.`
<br/>
<br/>
`<swan --> swimmer>. %0.90%`
<br/>
<br/>
`// Swan is a type of bird.`
<br/>
<br/>
`<swan --> bird>.`
<br/>
<br/>
`3`
<br/>
<br/>
`// I guess bird is a type of swimmer.`
<br/>
<br/>
`// OutputMustContain('<bird --> swimmer>. %0.90;0.45%')`
<br/>
<br/>
`// I guess swimmer is a type of bird.`
<br/>
<br/>
`// outputMustContain('<swimmer --> bird>. %1.00;0.42%')`

------------------------------------------- **Exemplification** -----------------------------------------------

`// Robin is a type of bird.`
<br/>
<br/>
`<robin --> bird>.`
<br/>
<br/>
`// A bird is a type of animal.`
<br/>
<br/>
`<bird --> animal>.`
<br/>
<br/>
`3`
<br/>
<br/>
`// I guess animal is a type of robin.`
<br/>
<br/>
`// outputMustContain('<animal --> robin>. %1.00;0.45%')`

------------------------------------------- **Conversion** -----------------------------------------------``

`// Bird is a type of swimmer.`
<br/>
<br/>
`<bird --> swimmer>.`
<br/>
<br/>
`// Is swimmer a type of bird?`
<br/>
<br/>
`<swimmer --> bird>?`
<br/>
<br/>
`6`
<br/>
<br/>
`// I guess swimmer is a type of bird.`
<br/>
<br/>
`// outputMustContain('<swimmer --> bird>. %1.00;0.47%')`

//---------------------------------------- **"Yes/No" Question** -------------------------------------------

`// Bird is a type of swimmer.`
<br/>
<br/>
`<bird --> swimmer>.`
<br/>
<br/>
`// Is bird a type of swimmer?`
<br/>
<br/>
`<bird --> swimmer>?`
<br/>
<br/>
`1`
<br/>
<br/>
`// Bird is a type of swimmer.`
<br/>
<br/>
`// OutputMustContain('<bird --> swimmer>. %1.00;0.90%')`

---------------------------------------- **"Wh" Question** -------------------------------------------

`// Bird is a type of swimmer.`
<br/>
<br/>
`<bird --> swimmer>. %1.00;0.80%`
<br/>
<br/>
`// What is a type of swimmer?`
<br/>
<br/>
`<?x --> swimmer>?`
<br/>
<br/>
`5`
<br/>
<br/>
`// Bird is a type of swimmer.`
<br/>
<br/>
`// outputMustContain('<bird --> swimmer>. %1.00;0.80%')`

-------------------------------------- **Backward Inference** -----------------------------------------``

`// Bird is a type of swimmer.`
<br/>
<br/>
`<bird --> swimmer>. %1.00;0.80%`
<br/>
<br/>
`// What is a type of swimmer?`
<br/>
<br/>
`<?1 --> swimmer>?  `
<br/>
<br/>
`5`
<br/>
<br/>
`// What is a type of bird?`
<br/>
<br/>
`// outputMustContain('<?1 --> bird>?')`
<br/>
<br/>
`// What is the type of bird?`
<br/>
<br/>
`// outputMustContain('<bird --> ?1>?')`
