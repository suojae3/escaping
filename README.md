<br/><br/>


## `@escaping` 키워드는 언제 사용하는 것일까?

<br/>

### 목차
- [`@escaping`키워드는 주로 두 가지 경우에서 사용된다]()
- [내부의 closure를 외부 변수에 저장하는 경우]()

<br/>

#

### `@escaping`키워드는 주로 두 가지 경우에서 사용된다

<br/>

&nbsp;&nbsp;&nbsp;&nbsp;<img src="escaping.png" width="400" height="200"><br/><br/>

1. 어떤 함수의 내부에 존재하는 closure를 외부 변수에 저장하는 경우
2. GCD(비동기 코드)를 활용해야하는 경우

<br/>

#

### 내부의 closure를 외부 변수에 저장하는 경우

<br/>



```swift
var aSavedFunction: (() -> ())?

func performEscaping2(closure: @escaping() -> ()) {
    aSavedFunction = closure 
}
```

1. fwe

<br/>

#

### GCD 비동기 코드를 사용하는 경우

```swift
func performEscaping(closue: @escaping() -> ()) {

    let name = "suojae"

    DispathcQueue.global().async {
        closure()
    }
}

```
