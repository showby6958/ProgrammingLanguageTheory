# 언어 설계의 기본 원칙 4가지
## 효율성(efficiency)
  - 목적 코드의 효율성: 실행이 얼마나 빠르게 되는가 
    예를 들어 파스칼, C언어는 타입 처리를 컴파일 시점에 해결하여 실행 시 효율적이다.
    반면 파이썬을 런타임 때 타입 체크를 하기 때문에 실행 속도가 느려진다.
## 일반성(generality)
  - 밀접하게 관련 있는 여러 개념들을 일반적인 하나의 개념으로 통합하여 얻는 성질
    일반성이 높다면, 다양한 문제와 상황에 유연하게 대처 가능
## 직교성(orthogonality)
  - 한 언어의 구성 요소가 문맥에 따라 다른 의미를 가져서는 안되는 성질
    예를 들어 매개 변수 전달에 있어 데이터 타입에 상관없이 동일한 전달 방식을 지원한다면, 직교성이 높다.
    C언어의 함수 호출 시 인자 전달 방식이 값에 의한 호출과 참조에 의한 호출을 지원한다. 이로 인해 코드 의미가 달라져서 직교성이 상대적으로 낮다.
## 획일성(uniformity)
  - 획일성은 비슷한 것은 비슷한 의미를, 다른 것은 다른 의미를 가져야 한다는 원칙이다.
  - C++의 클래스 정의는 세미콜론이 필요하지만, 함수 정의에는 세미콜롬이 없어야함
    class A{...};
    void f{...} 

# 기타 설계 원칙 8가지
## 표현력(expressiveness_
  - 표현력은 언어가 복잡한 과정이나 구조를 얼마나 쉽게 표현할 수 있는지를 의미한다.
  - 언어가 편리하게 다양한 연산을 지원하면 좋을것 같지만, 언어가 다양한 연산을 지원할수록 프로그램이 복잡해 질 수 있다.
  - 따라서 간결성이 낮아진다.
## 간결성(simplicity)
  - 간결성은 표현력과 상충되는 개념으로, 코드이 간결함과 명료함을 중시한다.
  - 표현력과 간결성을 균형있게 유지하는 것이 중요하다.

## 정확성(preciseness)
  - 정확성은 프로그램의 실행을 예측할 수 있도록 언어에 대한 정확한 정의가 있는지를 확인하는 원칙이다.
  - 언어에 대한 정확한 정의는 프로그램과 번역기의 신뢰성에 도움을 준다.
  - 정확성을 높이기 위해 표준화 기구에서 언어의 표준을 정하기도 함
  - 이를 통해 언어의 구현과 사용에 일관성을 제공할 수 있다.

## 기계 독립성(machine independence)
  - 언어가 특정 기계에 의존적이지 않고, 독립적인 것을 의미
  - 메모리 할당이나 기계 구조 등의 내용과는 독립적인 미리 정의된 데이터 타입을 제공하면 기계 독립성이 높다고 볼 수 있다.
  - 예를 들어 C언어의 경우 limits.h라는 헤더 파일이 있어서 미리 헤더에서 정의를 할 수 있다.

## 제약성(restrictability) = 부분성(subset)
  - 언어에 대한 최소한의 지식과 일부 언어 구조만 알아도 프로그램을 작성할 수 있는 성질이다.
  - 제약성이 높은 언어는 학습하기 쉽고, 빠르게 프로그래밍을 시작할 수 있게 된다.
  - 제약성이 높은 예시로 Lisp가 있다. 문법 자체가 복잡하지 않아 많은 지식 없이도 프로그램을 바로 작성할 수 있다.

## 보안성(security)
  - 프로그래밍 오류를 줄이고 오류 발견을 쉽게 하는 언어를 설계하는 원칙이다.
  - 신뢰성과 정확성에 밀접한 연관을 가지고 있으며, 프로그래머가 범할 수 있는 오류를 최소화하기 위한 속성이다.
  - C언어의 경우 포인터 연산이 자유로워 오류 발생이 높아 보안성이 낮다고 볼 수 있다.
  - 반면 Java와 같은 언어는 포인터 연산을 허용하지 않고 가비지 컬렉터를 통한 메모리 관리 기능을 제공하여 보안성이 높다.

## 확장성(extensibility)
  - 사용자가 언어에 새로운 기능을 추가할 수 있도록 하는 성질이다.
  - 사용자가 새로운 타입을 정의하는 것, 라이브러리에 새로운 함수를 추가하는 것, 번역기에 새로운 키워드를 추가하는 것 등을 예시로 든다.
  - 확장성이 좋은 언어로 Lisp가 있다. 매크로를 통해 언어를 확장할 수 있다.

## 기존 표기나 규칙과의 일관성
  - 언어 설계 시 표준화된 특성과 개념을 갖도록 한다.
  - 표준화된 표기를 잘 따르지 않은 언어 - Alogol 68 (type 대신 mode 사용)

