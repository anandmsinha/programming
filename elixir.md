Types in elixir 

1. integer
2. float = 1.0
3. boolean
4. atom - :atom are just constants they don't have any value
5. list [1, 2, 3]
6. tuple {1, 2, 3}

Operators

1. or, and, not - they are boolean operators and only accept boolean operators
2. ||, &&, ! they accept arguments of all type. for them all values except false and nil will evaluate to true
3. Elixir also has - ==, !=, ===, !==, <=, >=, < and > operators
4. overall osrting order number < atom < reference < functions < port < pid < tuple < maps < list < bitstring


__Functions__  

Defining anonymous functions
```ruby
add = fn a, b->
	a + b
end
```

1. mul(1, 2)
2. mul 1, 2 # also valid
3. To call an anonymous function use add.(1, 2) '.' is necessary

__Strings__
1. Exlixir supports string interpolation ex ```"hello #{:world}"```
2. To print on screen use ```IO.puts "Hello world"```
3. Length of string ```String.length(str)```
4. Single quoted string and double quoted strings are diffrent in elixir
5. String cocatenation is done via "<>" operator

__General__

1. To get code's point value use ? oprator. ```?a -> returns 97```
2. Binary string can be defined using <<>>. A binary is just a sequence of bytes


__Loops__

Switch

```erlang
case {1, 2, 3} do
	{4, 5, 6} ->
    	"won't match"
    {1, x, 3} ->
    	"This would match and bind x to 2"
    _ ->
    	"This would match anything."
    // To pattern match against existing variables we have to use ^ operator
    ^x ->
    	"This would match x defined earlier."
    // clauses also allow extra conditions
    {1, x, 3} when x > 0 ->
    	"will match and assign according to conditions"
 end
```

case is good when you need to macth against multiple values however if we want to check multiple conditions and find the first one which matches we use cond.

```erlang
cond do
	2 + 2 == 5 ->
    	"won't match"
    2 + 3 == 5 ->
    	"will match"
 end
```
If any condition does not macth error is raised  so always add a default condition true. In condition any value except false and nil is true

If

```erlang
if true do
	"This works"
end
// There can be else block also
// do end can also be replaced by
if true, do: (
	// all logic
)
```

Unless

```erlang
unles true do
	"something"
end
```

__Data structures__

1. Linked list or normal lists they are represented by []
2. Tuples are normal array that is continious in memory. a = {1, 2, 3}
3. Getting elements at index in tuple - ```elem(a, 1)```
4. Elixir data types are immutable to put at an index in tuple ```put_elem(a, 1, "world")``` this will return a new tuple.
5. To add element to list a = [], do a ++ 2
