# monkey

An interpreted language written in Go, as described in [Write an interpreter in Go](https://interpreterbook.com) ([Go言語でつくるインタプリタ](https://www.oreilly.co.jp/books/9784873118222/)) 

## Run REPL

```shell
$ git clone https://github.com/nao23/monkey
$ cd monkey
$ go run main.go

Hello nao23! This is the Monkey programming language!
Feel free to type in command
>> "HELLO"
HELLO
```

## The Monkey language

https://monkeylang.org


### Data Types
#### Integer 

```shell
>> 1
1
>> -1
-1
```

#### Boolean

```shell
>> true
true
>> false
false
```

#### String

```shell
>> "HELLO"
HELLO
>> "HELLO" + " WORLD"
HELLO WORLD
```

#### Array

```shell
>> [1, 2, 3]
[1, 2, 3]
>> [1, 2, 3][2]
3
>> [1, "a", true][2]
true
```

#### Hash

```shell
>> {"a": 1, "b": 2, "c": 3}["b"]
2
>> {1: "x", "b": 2, true: 3}[true]
3
```

### Operator

#### arithmetic operators

```shell
>> 1 + 2
3
>> -1 + 5
4
>> 3 - 1
2
>> 2 * (3 + 4)
14
>> 2 * (3 + 4) + 8 / 4
16
```

#### comparison operators

```shell
>> 1 < 2
true
>> 1 > 2
false
>> 1 == 1
true
>> 1 != 1
false
```

#### boolean operators

```shell
>> !(true)
false
```

### Assignment

```shell
>> let a = 1
>> a
1
>> let b = 2
>> a + b
3
```

### If-else Statement

```shell
>> if (1 < 5) { 1 }
1
>> if (1 > 5) { 1 } else { 2 }
2
```

### Function

```shell
>> let add = fn(a, b) { a + b };
>> add(1, 2)
3
>> let sub = fn(a, b) { a - b };
>> sub(3, 1)
2
```

high order function:
```shell
>> let applyFunc = fn(a, b, func) { func(a, b) }
>> applyFunc(2, 2, add)
4
>> applyFunc(10, 2, sub)
8
```

closures:
```shell
>> let newAdder = fn(x) { fn(y) { x + y } }
>> let addTwo = newAdder(2)
>> addTwo(3)
5
```

### Builtin functions

```shell
>> len("ABC")
3
>> len([1, 2, 3])
3
>> first([1, 2, 3])
1
>> last([1, 2, 3])
3
>> rest([1, 2, 3])
[2, 3]
>> push([1, 2], 3)
[1, 2, 3]
>> puts("HELLO")
HELLO
null
```
