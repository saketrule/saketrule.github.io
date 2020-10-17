#1 Learn you a Haskell for the greater good

This note is meant to log interesting trivia or quick notes as I go through the Haskell tutorial for a refresher. To start with, I'll be going through the following tutorial which is universally used to get started with Haskell - [learn-you-a-haskell](http://learnyouahaskell.com/!)


### 1. Introduction [(link)](http://learnyouahaskell.com/introduction!)
To get started, we'll be installing the recommended haskell package with the Glasgow Haskell Compiler, Cabal build system and the Stack tool for developing projects. This includes the interactive mode `ghci` . Functions in a file can be loaded using `:l myfunctions.hs` and reloaded using `:r`. Something similar to the Vim commands.



### 2. Starting Out [(link)](http://learnyouahaskell.com/starting-out!)
*  
	```
	-- The ++ operator loops over the first list argument, hence is linear in time
	[1,2,3,4] ++ [9,10,11,12]  

	-- The cons operator (:) however is constant time
	'A':" SMALL CAT" 
	23:[23,32]

	-- [1,3,4] is synctactic sugar for 1:3:4:[]
	[1,3,4] == 1:3:4:[]

	-- List supports the following operations (head, tail) / (init, last)
	-- null checks if a list is empty
	-- reverse, take, !!, length, minimum, maximum, sum, product are other list functions
	-- elem tests for element inclusion in list
	-- drop drops first n items from the list
	-- cycle infinitely cycles a list, repeat infinitely repeats an element, replicate repeats an element given number of times

	-- fst and snd are functions for Tuples
	```


### 3. Types and Typeclasses [(link)](http://learnyouahaskell.com/types-and-typeclasses!)
* 
	```
	-- Types: Int for memory bounded integer, Integer type for unbounded integer

	```

* Polymorphic functions - Functions which use type variables
* To run multiline command in ghci, for example if you want to have function type declaration, 

	```hk
	:{
	lucky :: Int -> String
	lucky a = show(a)
	:}
	```

* Typeclasses to know - Eq, Ord, GT, LT, Show, Read, Enum, Bounded, Num.
* fromIntegral is useful to convert Int to Num which is a more generic class
	```hk
	-- Does not work 
	read "4"

	-- Works because the return type is sucessfully inferred
	read "4" + 4
	read "4" :: Int
	```

### 4. Syntax in Functions [(link)](http://learnyouahaskell.com/syntax-in-functions!)

* Tried writing a `isSeven` function.

	```hk
	-- The following attempt failed - 
	:{
	isSeven :: (Num a) => a -> Bool
	isSeven x = x==7
	:}

	-- Eq is required for correct type inference
	:{
	isSeven :: (Eq a, Num a) => a -> Bool
	isSeven x = x==7
	:}
	```

* Patten matching function syntax. Note that the function definition changes

 ```hk
Prelude> myName "Saket" = "Yes it is"
Prelude> myName "Other" = "Maybe it is"
Prelude> :t myName
myName :: [Char] -> [Char]
Prelude> myName x = x
Prelude> :t myName
myName :: p -> p
Prelude> 
 ```

* Patterns - pattern matching decomposition while keeping reference to original item : `mylist@(x:y:xs)


* `let <bindings> in <expression>` is an expression, the bindings are only defined in local scope
* To define several bindings in a single line, separate them with a semicolon `;`. 

 ```hk
-- This does not work
let (a=2)
-- This does not work
(let a=2)
-- This works
(let a=2 in a)
(let a=2; b=3 in a*b)
 ```

* I have a hunch that case expressions won't be used a lot unlike guards and pattern matching, so including syntax here - 

 ```hk
 case expression of pattern -> result  
                   pattern -> result  
                   pattern -> result  
                   ...  
 ```

### 5. Recursion [(link)](http://learnyouahaskell.com/recursion!)
* How to break with an error - ` error "Error" `
* Infinite lists work
 ```hk
-- Works (Kudos)
repeat' x = x:repeat' x  
take 5 (repeat' 10)
```

* Guards expression cannot pattern match, must be an expression evaluating to Boolean

 ```hk
-- My Quicksort implementation
:{
quickSort :: (Ord a) => [a] -> [a]
quickSort [] = []
quickSort list@(x:xs) = lt' x xs ++ [x] ++ gt' x xs
 where lt' x xs = [y | y<-xs, y<=x]
       gt' x xs = [y | y<-xs, y>x]
:}
 ```

### 6. Higher Order Functions [(link)](http://learnyouahaskell.com/higher-order-functions)
* Multi parameter functions are all curried functions. The parameters are accepted via function application
* `takeWhile <f> <list>` , `zipWith <f> <list> <list>`
* Collatz sequence : 
```hk
:{
collatz :: (Integral a) => a -> [a]
collatz x
  | x==1 = [1]
  | even x = x  : collatz (x `div` 2)
  | odd x = x : collatz (3*x + 1)
  | otherwise = error "Unexpected argument encountered"

-- Number of integers in [0..100] with length of collatz sequence greater than 15
length (filter (>15) (map length (map collatz [1..100]) ) )
:}
```
* Lambdas ` \x a -> x+a `



