---
title: Fibonacci
url: language-guide/fibonacci
---

## Fibonacci

```
@fib n 2 -> [:1] {
    (n < 1) => end "Invalid Number of Terms!\0"
    (n = 1) => end "0\0"
    (n = 2) => end "0 1\0"

    %arg1 2 = 1
    %arg2 2 = 0

#loop
    ;temp = ([arg1] + [arg2])

    'arg2 : arg1
    'arg1 : temp

    $printf "%d\n\0", temp 
    'n --
    (n > 0) => jmp loop

    end "Done!\0"
}

#main
    $puts <- *fib 9
    &ext 0
```
