Math
====

Math.Ceiling
------------
Rounds up a floating point number to the nearest integer above it, if the float has a fractional part. If exactly equal to an integer, returns that integer.

Overloads
~~~~~~~~~
1. **Math.Ceiling(Double value): Double**

Sample::

  Math.Ceiling(13.2) == 14;

Math.CreateRectangle
--------------------
Creates a new RectangleObject with the width and height specified as floating point numbers.

Overloads
~~~~~~~~~
1. **Math.CreateRectangle(Double width, Double height): RectangleObject**

Sample::

  RectangleObject rectangle = Math.CreateRectangle(13.1, 2.4);

Math.CreateRectangleXY
----------------------
Creates a new RectangleXYObject with the leftmost coordinate, the topmost coordinate, the width and the height specified as floating point numbers.

Overloads
~~~~~~~~~
1. **Math.CreateRectangleXY(Double left, Double top, Double width, Double height): RectangleXYObject**

Sample::

  RectangleXYObject rectangleXY = Math.CreateRectangle(0.0, 4.0, 0.0, 1.0);


Math.Floor
----------
Rounds down a floating point number to the nearest integer below it, if the float has a fractional part. If exactly equal to an integer, returns that integer.

Overloads
~~~~~~~~~
1. **Math.Floor(Double value): Double**

Sample::

  Math.Floor(13.7) == 13;

Math.Modulus
------------
Returns the modulus or absolute value of a number. i.e. if the number is negative, it returns that number multiplied by (-1), and if the number if positive, it returns the number unchanged.

Overloads
~~~~~~~~~~
1. **Math.Modulus(Int value): Object**
2. **Math.Modulus(Double value): Object**

Sample::

  Math.Modulus(-3) == 3;
  Math.Modulus(3) == 3;

Math.PopulationStandardDeviation
--------------------------------
Calculates the population standard deviation of a collection of floating point values.

Overloads
~~~~~~~~~
1. **Math.PopulationStandardDeviation(Double[] values): Double**

- values is a collection of Doubles
- The collection must not be null
- The collection must not be empty

Sample::

  Double[] values = Collection.Create(12.2, 2.1, 7.8);
  Double popStdDev = Math.PopulationStandardDeviation(values);

Math.PopulationVariance
-----------------------
Calculates the population variance of a collection of floating point values.

Overloads
~~~~~~~~~
1. **Math.PopulationVariance(Double[] values): Double**

- values is a collection of Doubles
- The collection must not be null
- The collection must not be empty

Sample::

  Double[] values = Collection.Create(12.2, 2.1, 7.8);
  Double popVar = Math.PopulationVariance(values);

Math.Round
----------
Rounds a floating point number to the nearest integer. If the number is exactly halfway between two integer, one of which is even and one of which is odd, it returns the even number. If exactly equal to an integer, returns that integer.

Overloads
~~~~~~~~~
1. **Math.Round(Double value): Double**

Sample::

  Math.Round(3.2) == 3;
  Math.Round(3.7) == 4;

Math.SampleStandardDeviation
----------------------------
Calculates the sample standard deviation of a collection of floating point values.

Overloads
~~~~~~~~~
1. **Math.SampleStandardDeviation(Double[] values): Double**

- values is a collection of Doubles
- The collection must not be null
- The collection must not be empty

Sample::

  Double[] values = Collection.Create(12.2, 2.1, 7.8);
  Double SSD = Math.SampleStandardDeviation(values);

Math.SampleVariance
-------------------
Calculates the sample variance of a collection of floating point values.

Overloads
~~~~~~~~~
1. **Math.SampleVariance(Double[] values): Double**

- values is a collection of Doubles
- The collection must not be null
- The collection must not be empty

Sample::

  Double[] values = Collection.Create(12.2, 2.1, 7.8);
  Double SV = Math.SampleVariance(values);

Math.Truncate
-------------
Rounds a floating point number to the nearest integer towards 0. Results are identical to Math.Floor for positive numbers. Alternatively, think of it as discarding the fractional part of the number and returning the integral part.

Overloads
~~~~~~~~~
1. **Math.Truncate(Double value): Double**

Sample::

  Math.Truncate(32.7865) == 32;
  Math.Truncate(-32.9012) == -32;