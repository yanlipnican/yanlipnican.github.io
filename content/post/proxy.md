---
title: "Proxy"
date: 2017-10-15T21:31:16+02:00
draft: false
summary: "In todays blog post we will try to implement basic reverse proxy in go."
image: "/proxy-img.jpg"
---
# Proxy

```go
package main

import "fmt"

type Greeter interface {
    Greet()
}

type DogGreeter struct {
    name string
}

func (g DogGreeter) Greet() {
    return g.name+": Bork Bork!"
}

func channel(g Greeter) {
    fmt.Println(g.Greet())
}

func main() {
    dog := DogGreeter{"Sparkles"}
    channel(dog)
}
```