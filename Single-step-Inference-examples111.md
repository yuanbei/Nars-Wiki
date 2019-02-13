//------------------------------------------------ Revision ------------------------------------------------------

// Bird is a type of swimmer.
<bird --> swimmer>.

// Bird is probably not a type of swimmer.
<bird --> swimmer>. %0.10;0.60%

1

// Bird is very likely to be a type of swimmer.
// outputMustContain('<bird --> swimmer>. %0.87;0.91%')

//------------------------------------------------ Deduction ------------------------------------------------------

// Bird is a type of animal.
<bird --> animal>.

// Robin is a type of bird.
<robin --> bird>.

3

// Robin is a type of animal.
// outputMustContain('<robin --> animal>. %1.00;0.81%')

