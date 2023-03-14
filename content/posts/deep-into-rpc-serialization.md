---
title: "RPC 漫谈：序列化问题"
date: 2023-03-14
categories: ['Tech']
draft: true
---
最近遇到一个由于 Golang Interface 底层实现，引发的线上 panic 问题，虽然根源在于赋值操作没有保护起来，却意外地发现了关于 interface 的一些有意思的底层细节。

-- Java
```java
public static void main(String args) {
    System.out.println("Hello World");
}
```

-- Groovy
```groovy
class Student {
    def name
    def age

    def test(closure) {
        closure()
        println 'test'
    }
}
```

-- Go
```go
import "fmt"
func main() {
    fmt.println("Hello World!")
}

type User struct {
	Name  string
	Email string
}
```

-- Python
```python
age = 3
if age > 18:
    print('your age is ', age)
    print('adult')
else:
    print('your age is ', age)
    print('teenager')
```
