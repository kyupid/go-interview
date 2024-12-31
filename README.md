# go-interview
- [pointer, channal, range 질문](https://medium.com/@ninucium/go-interview-questions-part-1-pointers-channels-and-range-67c61345cf3c)
- [100문항 질문&답변](https://www.turing.com/interview-questions/golang)
- [초보자, 경험자 기준으로 나누어서 질문 14개 항목](https://www.interviewbit.com/golang-interview-questions/)

- 
### 1. **Go의 고루틴과 채널**
고루틴과 채널의 작동 원리를 설명하고, 고루틴 간 데이터를 안전하게 교환하기 위해 채널을 사용하는 간단한 예제를 작성하세요.



### 2. **인터페이스와 타입**
다음 코드에서 발생하는 문제를 찾고 수정하세요. 그리고 인터페이스와 타입 간의 관계를 설명하세요.
 ```go
 type Shape interface {
     Area() float64
 }

 type Square struct {
     Side float64
 }

 func main() {
     var s Shape = Square{Side: 5}
     fmt.Println(s.Area())
 }
 ```


### 3. **defer의 동작**
`defer`의 동작 방식을 설명하고, 아래 코드의 출력 결과를 예측하세요.
 ```go
 func main() {
     defer fmt.Println("World")
     fmt.Println("Hello")
 }
 ```

### 4. **Go에서의 포인터 사용**
다음 코드에서 `nil` 포인터로 인한 문제를 방지하려면 어떻게 수정해야 하나요?
 ```go
 type Node struct {
     Value int
     Next  *Node
 }

 func main() {
     var head *Node
     head.Next = &Node{Value: 10}
 }
 ```

### 5. **struct와 메소드**
Go의 struct와 메소드의 작동 원리를 설명하고, 아래 코드를 수정하여 `Circle`의 넓이를 계산하는 메소드를 추가하세요.
```go
type Circle struct {
   Radius float64
}
```

### 6. **concurrency 제어**
`sync.WaitGroup`를 사용하여 여러 고루틴을 동기화하는 프로그램을 작성하세요. 고루틴은 각각 1초 동안 대기한 후 자신이 끝났음을 출력합니다.

### 7. **패키지와 모듈**
Go의 패키지와 모듈 시스템을 설명하고, 새로운 모듈을 초기화하고 종속성을 관리하는 기본 단계를 나열하세요.

### 8. **select와 채널**
`select` 구문을 사용하여 두 개의 채널에서 데이터를 동시에 처리하는 프로그램을 작성하세요. 채널 중 하나는 1초마다 데이터를 보내고, 다른 채널은 2초마다 데이터를 보냅니다.

### 9. **에러 처리**
Go에서 에러 처리의 일반적인 패턴을 설명하고, 아래 코드에서 발생할 수 있는 에러를 처리하도록 수정하세요.
```go
func divide(a, b int) int {
   return a / b
}

func main() {
   result := divide(10, 0)
   fmt.Println(result)
}
```

### 10. **Go의 메모리 관리**
Go에서 가비지 컬렉션의 작동 원리를 간단히 설명하고, 아래 코드를 실행했을 때 메모리 누수가 발생할 가능성이 있는지를 분석하세요.
 ```go
 func leakyFunction() *[]int {
     arr := make([]int, 100)
     return &arr
 }

 func main() {
     leaky := leakyFunction()
     fmt.Println(len(*leaky))
 }
 ```
