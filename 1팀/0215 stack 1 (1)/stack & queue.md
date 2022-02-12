## Stack & Queue 가볍게 훑어보기



### Stack

- 한쪽 끝에서만 자료를 넣고 뺄 수 있는 자료구조

- `list`를 이용한다.
- 마지막에 넣은 것이 먼저 나오기 때문에, **LIFO (Last In First Out)** 이라고도 한다.



구현하거나 사용가치 있는 기능

```
push 스택에 자료 넣는 연산
pop 빼는 연산 (가장 위에꺼)
top 스택에서 가장 위에 있는 자료를 반환
empty 비어있는지 아닌지 여부를 반환
size 스택에 저장된 자료의 개수를 반환
```



class 말고 함수로 구현 한다면?

```python
import sys

new = []
for i in range(int(input())):
    func = sys.stdin.readline().strip()
    if func[:4] == 'push':
        a,b = func.split()
        new.append(int(b))
    elif func == 'pop':
        if len(new)==0:
            print(-1)
        else:
            print(new.pop())
    elif func =='size':
        print(len(new))
    elif func == 'empty':
        print( 0 if len(new) else 1 )
    else:
        print( new[-1] if len(new) else -1 )
```





### Queue

- 한쪽으로만 자료를 넣고, 다른 한쪽 끝에서만 뺄 수 있는 자료구조
- 먼저 넣은 것이 가장 먼저 나오기 때문에 **(FIFO) First In First Out**
- `BFS`알고리즘(그래프 체크) 에서 주로 사용한다.



- `list` 는 비추천, `collection`의 `deque`를 이용한다.

  ```python
  from collections import deque  # deque : 양방향 큐 (stack과 큐 모두 가능)
  
  test001 = deque()   # 생성
  ```

  - `deque.append(item)`: item을 데크의 오른쪽 끝에 삽입한다.
  - `deque.appendleft(item)`: item을 데크의 왼쪽 끝에 삽입한다.
  - `deque.pop()`: 데크의 오른쪽 끝 엘리먼트를 가져오는 동시에 데크에서 삭제한다.
  - `deque.popleft()`: 데크의 왼쪽 끝 엘리먼트를 가져오는 동시에 데크에서 삭제한다.
  - `deque.extend(array)`: 주어진 배열(array)을 순환하면서 데크의 오른쪽에 추가한다.
  - `deque.extendleft(array)`: 주어진 배열(array)을 순환하면서 데크의 왼쪽에 추가한다.
  - `deque.remove(item)`: item을 데크에서 찾아 삭제한다.
  - `deque.rotate(num)`: 데크를 num만큼 회전한다(양수면 오른쪽, 음수면 왼쪽)
