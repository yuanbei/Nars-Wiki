//---------------------------------------------- Revision ----------------------------------------------------

// Bird is a type of swimmer.

<bird --> swimmer>.

// Bird is probably not a type of swimmer.

<bird --> swimmer>. %0.10;0.60%

1

// Bird is very likely to be a type of swimmer.

// outputMustContain('<bird --> swimmer>. %0.87;0.91%')

//---------------------------------------------- Deduction ---------------------------------------------------

// Bird is a type of animal.

<bird --> animal>.

// Robin is a type of bird.

<robin --> bird>.

3

// Robin is a type of animal.

// outputMustContain('<robin --> animal>. %1.00;0.81%')

//---------------------------------------------- Induction---------------------------------------------------

// Swan is a type of swimmer. 

<swan --> swimmer>. %0.90%

// Swan is a type of bird. 

<swan --> bird>. 

3

// I guess bird is a type of swimmer.

// OutputMustContain('<bird --> swimmer>. %0.90;0.45%')

// I guess swimmer is a type of bird.

// outputMustContain('<swimmer --> bird>. %1.00;0.42%')

//------------------------------------------- Exemplification -----------------------------------------------

// Robin is a type of bird.

<robin --> bird>.

// A bird is a type of animal.

<bird --> animal>.

3

// I guess animal is a type of robin. 

// outputMustContain('<animal --> robin>. %1.00;0.45%')

//------------------------------------------- Conversion -----------------------------------------------

// Bird is a type of swimmer. 

<bird --> swimmer>.

// Is swimmer a type of bird?

<swimmer --> bird>? 

6

// I guess swimmer is a type of bird.

// outputMustContain('<swimmer --> bird>. %1.00;0.47%')

//---------------------------------------- "Yes/No" Question -------------------------------------------

// Bird is a type of swimmer.

<bird --> swimmer>.

// Is bird a type of swimmer?

<bird --> swimmer>? 

1

// Bird is a type of swimmer.

// OutputMustContain('<bird --> swimmer>. %1.00;0.90%')

//---------------------------------------- "Wh" Question -------------------------------------------

// Bird is a type of swimmer.

<bird --> swimmer>. %1.00;0.80%

// What is a type of swimmer?

<?x --> swimmer>?  

5

// Bird is a type of swimmer.

// outputMustContain('<bird --> swimmer>. %1.00;0.80%')


//-------------------------------------- Backward Inference -----------------------------------------

// Bird is a type of swimmer.

<bird --> swimmer>. %1.00;0.80%

// What is a type of swimmer?

<?1 --> swimmer>?  

5

// What is a type of bird?

// outputMustContain('<?1 --> bird>?')

// What is the type of bird?

// outputMustContain('<bird --> ?1>?')