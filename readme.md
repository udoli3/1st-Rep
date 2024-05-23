# AIFFEL Campus Code Peer Review Templete
- 코더 : 김원영
- 리뷰어 : 김재이


# PRT(Peer Review Template)
[ㅇ]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
- 문제에서 요구하는 기능이 정상적으로 작동합니다.
```
문제1
def find_min_max(numbers):
    min_value = float('inf')
    max_value = float('-inf')

    def update_min_max(num):
        nonlocal min_value, max_value
        if num < min_value:
            min_value = num
        if num > max_value:
            max_value = num

    for num in numbers:
        update_min_max(num)

    def get_min():
        return min_value

    def get_max():
        return max_value
    return get_min, get_max

결과:
최솟값: 3
최댓값: 12

문제2
코드:
def counter(func):
    def wrapper(*args, **kwargs):
        wrapper.count += 1
        print(f"{func.__name__} 실행횟수: {wrapper.count}")
        return func(*args, **kwargs)
    wrapper.count = 0
    return wrapper

@counter
def say_hello():
    print("Hello Aiffel!")

for i in range(5):
    say_hello()

결과물:

say_hello 실행횟수: 1
Hello Aiffel!
say_hello 실행횟수: 2
Hello Aiffel!
say_hello 실행횟수: 3
Hello Aiffel!
say_hello 실행횟수: 4
Hello Aiffel!
say_hello 실행횟수: 5
Hello Aiffel!
```
    
[ㅇ]  **2. 핵심적이거나 복잡하고 이해하기 어려운 부분에 작성된 설명을 보고 해당 코드가 잘 이해되었나요?**
- 특히 문제2에서 주석으로서 실행하시는 프로그램 구조가 잘 눈에 보이도록 설명해주셨습니다.
```
#데코레이터 함수의 내부 함수(wrapper)에서 원래 함수(func)를 호출을 위해 함수이름.__name__으로 지정
#내부 함수(wrapper)에서 실행 횟수를 기록
#초기 실행 횟수를 0으로 설정
#say_hello 함수에 @counter 데코레이터를 적용
```
      
[ㅇ]  **3. 에러가 난 부분을 디버깅하여 “문제를 해결한 기록”을 남겼나요? 또는 “새로운 시도 및 추가 실험”을 해봤나요?**
- 문제2를 도전하실 때, 출력 내용이 반순차적으로 출력되는 부분이 있었고, 해결하신 것을 알 수 있었습니다. 파일에 기록되어 있지는 않지만, 피어리뷰에서 잘 설명해주셨습니다.
        
[ㅇ]  **4. 회고를 잘 작성했나요?**
- 프로젝트 결과물에 대해 배운점이 잘 적혀있습니다.
```
회고 1
find_min_max 함수는 find_min과 find_max 함수를 반환하며 이 두 함수는 주어진 숫자 리스트 numbers의 최솟값과 최댓값을 반환하게 되는데 클로저를 사용하여 min_value와 max_value 변수를 외부에 노출하지 않고도 최솟값과 최대값을 찾을 수 있다.
더불어 find_min_max 함수가 호출된 이후에도 find_min과 find_max 함수를 통해 min_value와 max_value 변수에 접근할 수 있는데 하기 코드를 실행하면 예측한데로 최솟값 3과 최댓값 12가 출력되는 것을 확인할 수 있다.

회고 2
하기 코드를 통해 counter 데코레이터는 함수가 실행될 때마다 실행 횟수를 기록하고 출력하도록 만들었으며 say_hello 함수에 @counter 데코레이터를 적용하여 실행 횟수를 추적하도록 명령하였다.
결론적으로 @counter 데코레이터를 적용하여 say_hello 함수를 수정하였으며 그 결과 이제 say_hello 함수를 호출할 때마다 실행 횟수가 증가하며 출력되는 것을 확인할 수 있다.
```
- 아쉬운점, 느낀점 역시 피어리뷰에서 공유해주셨습니다. wrapper 함수 부분에서 매개변수를 지정하신 부분을 의논했을 때는 매개변수 없이 하는 프로그래밍과의 차이를 같이 고민할 수 있었습니다.
 
