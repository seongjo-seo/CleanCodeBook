# 06장 객체와 자료 구조
변수를 private로 정의하는 이유는 남들이 변수에 의존하지 않게 만들고 싶어서다.<br/>
잘못된 코드 구현은 private를 public과 동일하게 사용하는 것과 같다.<br/>

- 자료 추상화<br/>

구체적인 Point 클래스
``` java
public class Point {
  public double x;
  public double y;
}
```
추상적인 Point 클래스
``` java
public interface Point {
  double getX();
  double getY();
  void setCartesian(double x, double y);
  double getR();
  double getTheta();
  void setPolar(double r, doulbe theta);
}
```

구체적인 클래스의 경우 직교좌표계를 사용하고 있으며, 개별적으로 좌푯값을 읽고 설정하게 강제한다. 하지만 private로 변수를 설정하여 getter/setter를 사용하더라도 외부로 값을 노출하여 구현한 것과 다름이 없다.<br/>

추상적인 클래스는 좌표를 읽을 때는 각 값을 개별적으로 읽어야 한다. 또한 메서드 접근 정책을 강제한다.<br/><br/>

변수 사이에 함수 계층을 추가해 봤자 구현이 감춰지는 것이 아니다. 구현을 감추려면 추상 인터페이스를 제공하여 구현 부분을 정확하게 알 수 없도록 만들어내는 것이 올바른 자료 추상화이다.<br/>

- 자료/객체 비대칭<br/>
객체는 추상화 뒤로 자료를 숨긴 채 자료를 다루는 함수만 공개한다.<br/>
자료 구조는 자료를 그대로 공개하며 별다른 함수를 제공하지 않는다.<br/><br/>

객체와 자료 구조는 근본적으로 양분되며, 다음과 같이 각각의 설명으로 정리할 수 있다.<br/><br/>
1. (자료 구조를 사용하는) 절차적인 코드는 기존 자료 구조를 변경하지 않으면서 새 함수를 추가하기 쉽다. 객체 지향 코드는 기존 함수를 변경하지 않으면서 새 클래스를 추기하기 쉽다.<br/>
2. 절차적인 코드는 새로운 자료 구조를 추가하기 어렵다. 그러려면 모든 함수를 고쳐야 한다. 객체 지향 코드는 새로운 함수를 추가하기 어렵다. 그러려면 모든 클래스를 고쳐야 한다.<br/><br/>

**즉, 객체 지향 코드에서 어려운 변경은 절차적인 코드에서 쉬우며, 절차적인 코드에서 어려운 변경은 객체 지향 코드에서 쉬워진다.**<br/>

- 디미터 법칙<br/>
디미터 법칙은 잘 알려진 휴리스틱(heuristic)으로, 모듈은 자신이 조작하는 객체의 속사정을 몰라야 한다는 법칙이다.<br/>
디미터 법칙을 조금 더 정리하면 다음과 같다.<br/>
"클래스 C의 메서드 f는 다음과 같은 객체의 메서드만 호출해야 한다."<br/><br/>

<br/>
(휴리스틱 : 불충분한 시간이나 정보로 인하여 합리적인 판단을 할 수 없거나, 체계적이면서 합리적인 판단이 굳이 필요하지 않은 상황에서 사람들이 빠르게 사용할 수 있게 보다 용이하게 구성된 간편추론의 방법이다.)<br/><br/><br/>

- 기차 충돌(train wreck)<br/>
```java
final String outputDir = ctxt.getOptions().getScratchDir().getAbsolutePath();
```
위와 같은 코드를 기차처럼 한 줄로 이뤄진 코드를 말하며, 피하는 것을 권장하는 방식이다.<br/>

```java
Options opts = ctxt.getOptions();
File scratchDir = opts.getScratchDir();
final String outputDir = scratchDir.getAbsolutePath();
```
위와 같이 코드를 분할하는 것을 권장한다.<br/>

- 잡종 구조<br/>
절반은 객체, 절반은 자료 구조인 잡종 구조가 존재하는데 잡종 구조의 경우 양쪽 개념의 단점만 모아놓은 구조다.<br/>


- 자료 전달 객체<br/>
자료 구조체의 전형적인 형태는 공개 변수만 있고 함수가 없는 클래스 형태이다.<br/>
자료 구조체를 때로는 자료 전달 객체라고 한다. DTO(Data Transfer Object, DTO).<br/>
데이터베이스와 통신하거나 소켓에서 받은 메시지의 구문을 분석할 때 유용하게 사용된다.<br/>
DTO는 데이터베이스에 저장된 가공되지 않은 정보를 애플리케이션 코드에서 사용할 객체로 변환하는 일련의 단계에서 가장 처음으로 사용되는 구조체이다.<br/>


- 활성화 레코드<br/>
활성 레코드는 DTO의 특수한 형태다.<br/>
활성 레코드에 비즈니스 규칙 메서드를 추가하는 것은 잡종 코드를 만드는 것과 다름이 없다. 이런 문제를 해결하기 위해서는 활성 레코드는 자료 구조로 취급하며, 비즈니스 규칙을 담으면서 내부 자료를 숨기는 객체는 따로 생성해주는 것이 좋다.<br/><br/>


### 정리
객체는 동작을 공개하고 자료를 숨긴다.<br/>
자료 구조는 별다른 동작 없이 자료를 노출한다.<br/>
기존 자료 구조에 새 동작을 추가하기는 쉬우나, 기존 함수에 새 자료 구조를 추가하는 행위가 어렵다.<br/>
개발자가 시스템을 개발할 때, 새로운 자료 타입을 추가하는 유연성이 필요하면 객체를. 새로운 동작을 추가하는 유연성이 필요하면 자료 구조와 절차적인 코드가 적합하다.<br/>
