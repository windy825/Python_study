## 파이썬만의 syntax sugar!!   for-else 구문





### 1. 그래서 어떻게 쓰는건데??

`for` 문을 이용하다 보면, 루프 중간에 `break`문으로 해당 구문 블록을 빠져나오는 경우들이 있습니다.

이때, `break`문에 걸려서 빠져나가는지 아닌지에 대한 판단이 필요할때가 있습니다.



- **`for-else` 구문 작동방식**

  `for`문이 `break`로 빠져나오지 않고 끝까지 실행되었을 경우 (내가 설정한 `break`조건이 발동이 안됬을때) 

  `else`문이 실행되게 됩니다.

  ```python
  for i in range(10):                           # 0~9까지 순회하면서
  	if i > 100:                               # 내가 설정한 조건으로 검사
  		print("break : 이게 진짜 된다고?")              
  		break                                 # 내가 설정한 if조건이 통과되면? break
  else:
  	print("else : 될리가 없잖아~")              # for문을 돌면서 한번이라도 break 없이, 끝까지 수행된다면? 실행
                                                
      
  >>>                                           # 실행 결과
  else : 될리가 없잖아~
  ```

  

  만약 `break` 가 없다면?

  ```python
  for i in range(10):                          
  	if i < 100:                               # 부호가 위 예시와 바뀜에 주의   
  		print("이게 진짜 된다고?")              
                            
  else:
  	print("else : break도 없네? 난 무조건이지!")         
    
  
  >>>                                           # 실행 결과
  이게 진짜 된다고?
  이게 진짜 된다고?
  이게 진짜 된다고?
  이게 진짜 된다고?
  이게 진짜 된다고?
  이게 진짜 된다고?
  이게 진짜 된다고?
  이게 진짜 된다고?
  이게 진짜 된다고?
  이게 진짜 된다고?                                # for문이 끝까지 순회
  else : break도 없네? 난 무조건이지!               # else도 실행됨
  ```





### 2. while문에도 적용 가능한가??

`while` 구문에도 쓸 수 있습니다.



- **while-else 구문 작동방식**

  ```python
  i = 1
  while i < 10 :
  	if i == 5:
  		print("break : 브레이크 등장!")                  # while문이 반복되다가, break문이 실행되면??
  		break
  	else:
  		print(i)
  	i +=1
  	
  else:
  	print("else : 브레이크가 안 걸렸네? 이건 기회야! 내 차례야")
  
      
  >>>                                           # 실행 결과
  1
  2
  3
  4
  break : 브레이크 등장!
  ```

  그런데 만약에, `while`문이 끝까지 수행되어도 `break`문이 실행이 안된다면?

  ```python
  i = 1
  while i < 10 :
  	if i == -999:
  		print("break : 브레이크 등장!")
  		break
  	else:
  		print(i)
  	i +=1	
      
  else:
  	print("else : 브레이크가 안 걸렸네? 이건 기회야! 내 차례야")
  
      
  >>>                                           # 실행 결과
  1
  2
  3
  4
  5
  6
  7
  8
  9
  else : 브레이크가 안 걸렸네? 이건 기회야! 내 차례야
  ```

  `for` 문과 마찬가지로, `break`가 안 쓰였다면?  `else`는 또 신나가지고 무조건 나옵니다.

  ```python
  i = 1
  while i < 10 :
  	if i == -999:
  		pass
  	else:
  		print(i)
  	i +=1
  	
  else:
  	print("else : 브레이크가 안 쓰였네? 난 무조건이지!")
      
      
  >>>                                           # 실행 결과
  1
  2
  3
  4
  5
  6
  7
  8
  9
  else : 브레이크가 안 쓰였네? 난 무조건이지!
  ```

  





### 3. 숙제??

추가 연습문제는 없습니다. 앞으로 만나시게 될 여러 문제들에서 해당 `for/while - else` 구문은 유용하게 쓰일 것 입니다.

자주 사용하시면서 연습하시면 좋습니다. (장점이 확실하니까요! 잘 써먹으면 좋겠죠?)



---

*end*