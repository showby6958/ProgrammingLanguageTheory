# 댕글링 포인터 관련
https://code-lab1.tistory.com/65

# 댕글링 포인터
- 유효한 객체를 가리키고 있지 않는 ptr
- 할당 해제된 memory를 ptr가 가리키는 경우
  ![image](https://github.com/user-attachments/assets/63d4f5b5-63b0-490d-8324-b182ff368c1a)
- 댕글링 포인터는 적절한 타입의 유효한 객체를 가리키고 있지 않은 포인터를 말한다. 예를 들어 이미 할당 해제된 메모리를 포인터가 계속 가리키고 있다면 해당 포인터는 댕글링 포인터이다.



# 댕글링 포인터 해결법
## Tombstone Approach
![image](https://github.com/user-attachments/assets/a06393eb-abe1-4705-8ff5-cd8289e99010)

첫번째 방법은 tombstone(비석)이라고 불리는 특별한 cell을 설정해 포인터가 할당된 객체를 직접 가리키지 않고 비석을 통해 가리키도록 하는 방법이다. 
 
- 예를 들어 [그림 3]처럼 ptr1을 free 한다면, 객체는 반환되고 해당 객체를 가리키던 비석은 nil이 된다. 만약 nil을 가리키는 포인터가 있다면 이것이 오류임을 검출할 수 있게 된다. 
 
비석 방법은 공간 낭비와 시간 낭비가 심하다



## Locks-and-keys
각 포인터는 (key, value)의 형태로 나타내어지는데, 이때 key는 정수 형태를 가진다.


![image](https://github.com/user-attachments/assets/d423611e-fe53-4aa6-a2a8-78188ec71c20)

- 예를 들어 [그림 4]처럼 동일한 객체를 가리키는 포인터 2개가 있을 때(동일한 객체를 가리키는 포인터는 동일한 key값을 가짐), 메모리를 해제하면 lock의 값이 key값과 다르도록 변경된다. 따라서 다른 포인터는 안전하게 비활성화된다.
