# 02장

가끔 블로그에 본인이 구현한 코드를 정리하고, 포스팅한 내용들을 다시 참조할 때 코드를 보고도 다시 읽어야 하는 경우가 종종 있었습니다.<br/>
코드를 봤을 때 무엇을 작업하는 코드인지 명확하게 해석하기 어려웠고, 그런 코드는 로직에 따라서 다시 읽으면서 학습을 진행했습니다.<br/><br/>
2장의 의미 있는 이름을 읽고 보니 다른 개발자분들이 제 코드를 참조할 때 제 설명을 읽는다 하더라도 중간중간에 다시 코드를 봐야 하는 번거로움이 있었을 것이라 생각됐습니다.<br/>

로직을 이해하는 부분 중 가장 이해가 오래 걸리는 부분은 반복문과 조건이라 생각했는데 변수가 어떤 방식으로 흘러 프로세스를 이루는지도 매우 중요한 부분이라고 생각이 들었습니다.<br/><br/>

#### 그릇된 정보를 피해라
정말 많은 공감이 됐던 맥락인 것 같습니다. 구글에서 다른 코드들을 참조할 때 O과 0의 차이 L의 소문자인 l과 1의 차이점이 헷갈리는 폰트를 갖고 있는 경우도 되게 많은 경험이 있었습니다.<br/>
폰트가 비슷하게 설정되어 있던 경우 더욱 찾기도 어려웠던 경험이 있었습니다.. 저 또한 이런 부분을 참조해서 프로젝트를 진행할 때 겹치지 않는 선에서 가능하면 대문자로 명사를 정의할 수 있도록 코드를 구현하는데 필요한 생각 외로 명명에도 많은 시간을 투자해야 함을 느꼈습니다.<br/><br/>

#### 발음하기 쉬운 이름을 사용하라
확실히 평소 발음이 어렵고 많은 내용을 품고 있는 코드보다 자주 사용되면서 발음도 쉬운 이름이 확연히 익숙하게 다가왔습니다. 그런 코드들이 눈에 더 잘 띄고 코드의 로직을 이해하는데 걸리는 시간도 적어서 더 좋았습니다.<br/><br/>

### 검색하기 쉬운 이름을 사용하라
Java에서 다양한 메소드를 사용하다 보면 로컬 변수를 다양하게 사용할 수도 있게 되는데 막상 전역 변수로 자주 사용되는 이름과 로컬 변수로 다양하게 사용되는 변수를 정리하여 분리하면 더 빠르게 찾아서 문제를 해결할 수 있을 것이라고 생각됐습니다.<br/><br/>

### 인코딩을 피해라
헝가리안 표기법이나 기타 인코딩 방식이 코딩에 방해가 된다는 얘기 또한 공감이 많이 됐습니다. 구글링을 하다 보면 예전에 작성된 포스팅에서 변수+타입의 형식으로 예를들면 boxString과 같이 작성된 코드들이 종종 보였습니다.<br/>
이런 코드들을 정리할 때 너무 긴 단어가 되면 코드 작성에 효율성을 낮출 수 있다고 생각됐습니다.<br/><br/>

### 자신의 기억력을 자랑하지 마라
책에서 의도는 타인이 이해하기 쉬운 코드를 내놓을 수 있도록 하는 것에 초점이 잡힌 것 같습니다.
그러나 저는 다음에 필요했을 때 스스로 찾아보기 어려운 부분이 공감 포인트가 될 수도 있겠다 생각했습니다.<br/>
본인이 기술 블로그를 시작한 여러 이유 중 큰 이유로 이전에 작성한 코드에서 의미를 제대로 찾지 못해서 그 내용을 정리하기 위해서 시작했던 부분도 있었습니다. 그래서 기억력을 자랑하고 무조건 그 생각에 틀에 박히지 않으려고 노력하고 학습을 추가로 나아갑니다. 잘못된 부분이 있다면 향후에 얼마나 시간이 지나도 제대로 이해할 수 있도록 수정한다면 정말 좋은 학습이 될 것이라 생각됩니다.<br/><br/>


### 클래스 이름
**'클래스 이름과 객체 이름은 명사나 명사구가 적합하다.'**<br/>
클래스는 하나의 객체 단위로 묶어서 코딩하기 때문에 여러 동작을 진행하는 객체가 명사로 묶이면 어떤 동작의 특성을 갖는지 이해하기 어렵기 때문이라 생각됐습니다.<br/><br/>

### 메서드 이름
메소드 이름은 클래스와 다르게 하나의 동작을 위한 기능 구현이 되는 경우가 많기 때문에 동사나 동사구가 적합하게 됩니다.<br/><br/>

### 기발한 이름은 피하라
이 문맥을 읽었을 때 유행어를 생각했습니다. 예전부터 꾸준히 써오던 단어는 꾸준히 사용되고 누가 들어도 대부분의 세대가 이해할 수 있습니다. 하지만 기발한 이름으로 유행어처럼 명칭을 작성하는 경우 그 명칭이 **유행어**의 시대가 지나고 난 뒤에 다시 생각하면 의미나 목적이 변해있을 수 있기 때문에 꾸준히 자주 사용되는 단어로 제대로 된 의도를 갖고 직관적으로 표현하는 것이 좋다고 생각됩니다.<br/><br/>

### 말장난을 하지 마라
A라는 변수가 있으면 A1, A2, A3라는 객체 3개로 예를 들지 않도록 노력해야 하는 것 같습니다. 한 단어를 두 가지 유사 목적으로 숫자만 추가해서 사용하는 경우 로직을 처리하는 과정에서 혼란이 생길 수 있다고 생각됩니다. <br/><br/>

### 의미 있는 맥락을 추가하라
알고리즘 체계적으로 읽힐 수 있도록 객체가 하나로 끝내는 것보다 객체에 필요한 메소드를 단위별로 정리하여 로직을 이행할 수 있도록 맥락을 만드는 것이 좋다고 생각됐습니다.<br/><br/>

### 불필요한 맥락을 없애라
기능들이 어떻게 사용될 것인지 어떤 이유로 열거하여 사용됐는지 고려하고 불필요한 경우에는 맥락을 효율적으로 없애는 것을 생각하는 것이 좋은 것 같습니다.<br/>
즉, 꼭 필요한 부분에 대해서는 맥락을 추가하지만 아니라면 없애는 것도 고려할 사항에 있다 생각됩니다. <br/><br/>
