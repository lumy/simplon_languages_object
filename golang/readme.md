# Golang (go)

https://golang.org/doc/install
https://tour.golang.org/basics/1

## Introduction

Golang, known as a better version of C does not implement all object concept.


## Entrypoint

During compilation, go will be looking for a function named `main`:
```golang
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

## Implicit and Explicit variable

Type is not strong but can be.
```golang
package main

import "fmt"

func main() {
	var i, j int = 1, 2
	k := 3
	c, python, java := true, false, "no!"

	fmt.Println(i, j, k, c, python, java)
}
```

As you see, you can use the word `var` you can precise the type of variable but you can omit it if
you use `:=`
