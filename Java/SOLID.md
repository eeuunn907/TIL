**객체지향 설계 과정**
1. 요구사항(제공해야 할 기능)을 찾고 세분화 한다. 그리고 그 기능을 알맞은 객체로 할당한다.
2. 기능을 구현하는데에 필요한 데이터를 객체에 추가한다.
3. 해당 데이터를 이용하는 기능을 구현한다. (기능은 최대한 캡슐화)
4. 객체 간에 어떻게 매소드를 호출을 주고받을 지 결정한다.

SOLID라고 부르는 5가지 설계원칙이 존재한다

**SRP (Single Responsibility) 단일 책임 원칙** <br>
"하나의 객체 또는 메소드는 하나의 책임만을 가져야한다." <br>
클래스 또는 메소드의 응집성을 높이고, 클래스 간의 결합도를 낮추는데 목적이 있다. 클래스가 하나의 책임에만 집중하게 되면, 해당 책임에 대한 변경이 필요할 때 다른 부분에 영향을 덜 주기 때문에 코드의 유지보수성과 확장성이 높아진다.
```java
//AreaCalculrator
public class AreaCalculrator{
    private final int width;
    private final int height;

    public AreaCalculrator(int width, int height){
        this.width = width;
        this.height = height;
    }

    //면적 구하기
    public int getArea(){
        return width * height;
    }
}

//AreaConverter
public class AreaConverter{
    //변환할 단위 상수들
    private static final double INCH_TERM = 0.0245d;
    private static final double FEET_TERM = 0.3048d;

    //인치로 변환
    public double metersToInches(int arae){
        return area / INCH_TERM;
    }

    //피트로 변환
    public double metersToFeet(int arae){
        return area / FEET_TERM;
    }
}
```
**OCP (Open-Closed) 개방-폐쇄 원칙** <br>
**LSP (Liskov Substitution) 리스코프 치환 원칙** <br>
**ISP (Interface Segregation) 인터페이스 분리 원칙** <br>
**DIP (Dependency Inversion) 의존 역전 원칙** <br>