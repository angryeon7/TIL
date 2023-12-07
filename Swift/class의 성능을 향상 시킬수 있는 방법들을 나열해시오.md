### **Heap 보다는 *Stack 메모리에 할당 한다.**

- class보단 struct나 enum을 사용한다.

class는 heap 할당, struct와 enum은 stack 할당.

> **Why?** 
메모리 할당과 해제는 스택이나 힙에서 처리되는데 스택은 LIFO의 단순한 구조로 힙에 비해 메모리의 구조가 간단해 비용이 적게 들어가며 더 빠르게 할당할 수 있습니다. struct는 stack을 사용하고 class 는 heap을 사용하기 때문에 class의 특성이 필요하지 않으면 struct로 변경하는 것이 성능개선에 좋습니다.
> 

---

### Dynamic Dispatch의 사용을 줄이는것

- 클래스는 Dynamic Dispatch로 동작합니다.
- 상속과 override를 할 수 있기 때문에 프로그램이 클래스가 어떤 메서드나 프로퍼티를 참조하는지 런타임에 결정해야 합니다. 메서드 테이블에서 메서드를 찾은 후 간접 호출을 통해 동작하도록 구현되어 있습니다. 간접 호출은 직접 호출보다 느리고, 비용이 더 듭니다.
- Dynamic Dispatch를 Static Dispatch로 바꿔주어 런타임 오버헤드(어떤 처리를 하기 위해 들어가는 간접적인 처리 시간, 메모리)를 줄이면 클래스의 성능이 향상됩니다.
1. **상속되지 않는 class 에는** `final`**키워드를 붙여준다**
    
    간접호출은 접근횟수마다 일정량의 오버헤드를 발생시키기때문에 최소화하는 것이 좋기때문에 `final 을 사용하여 클래스, 메소드, 속성이 오버라이드 할 수 없도록 제약`하면 class의 성능을 향상시킬 수 있습니다. 
    
2. `private 키워드를 사용`
    
    private 키워드를 사용하면 같은 파일내에 오버라이딩 선언이 없을 시, 컴파일러가 자동으로 dynamic call을 직접호출로 대체하므로 `private 키워드를 사용`하는 방법도 있습니다.
    
    : 오버라이드 할 일이 없다. → 한개뿐임→ V-Table 참조할 일이 없음 
    

---

### **Reference counting을 적게 만든다.**

Reference counting 말 그대로 참조된 인스턴스의 개수를 세는 것입니다. Heap 영역에 할당하는 것 자체가 레퍼런스를 사용하기 때문에 reference counting이 발생합니다.

- **class** 에서 *String, Dictionary, Set, Array*와 같은 **가변길이 (길이가 고정적이지 않은) Collection 타입**의 변수 사용을 줄입니다.

> **Why?**
> 
> 
> string은 struct 타입이지만 문자열의 콘텐츠를 heap에 저장하기 때문
> 
> 크기가 가변적이면 참조를 하게됨
>
