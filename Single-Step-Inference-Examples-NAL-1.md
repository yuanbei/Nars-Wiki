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

//---------------------------------------------- Exemplification ---------------------------------------------------

// Swan is a type of swimmer. 

<swan --> swimmer>. %0.90%

// Swan is a type of bird. 

<swan --> bird>. 

3

// I guess bird is a type of swimmer.

// OutputMustContain('<bird --> swimmer>. %0.90;0.45%')

// I guess swimmer is a type of bird.

// outputMustContain('<swimmer --> bird>. %1.00;0.42%')

