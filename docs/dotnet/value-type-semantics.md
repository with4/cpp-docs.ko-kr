---
title: "값 형식 의미 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__pin 키워드"
  - "상속, 값 형식"
  - "interior_ptr 키워드[C++]"
  - "pin_ptr 키워드[C++]"
  - "포인터 고정"
  - "가상 함수, 값 형식"
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 값 형식 의미
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 값 형식 의미가 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 다음은 Managed Extensions for C\+\+ 사양에 사용되는 정식 단순 값 형식입니다.  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
```  
  
 Managed Extensions에서는 값 형식의 네 가지 구문 변형이 사용됩니다. 여기서 형식 2와 3은 의미가 동일합니다.  
  
```  
V v = { 0 };       // Form (1)  
V *pv = 0;         // Form (2) an implicit form of (3)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0; // Form (4) must be local   
```  
  
## 상속된 가상 메서드 호출  
 `Form (1)`은 정식 값 개체입니다. `ToString()` 같은 상속된 가상 메서드를 호출하려고 하는 경우를 제외하고는 그 의미를 쉽게 이해할 수 있을 것입니다.  예를 들면 다음과 같습니다.  
  
```  
v.ToString(); // error!  
```  
  
 이 메서드는 `V`에서 재정의되지 않으므로 이 메서드를 호출하려면 컴파일러가 기본 클래스의 관련 가상 테이블에 액세스해야 합니다.  값 형식은 해당 가상 테이블\(vptr\)에 대한 관련 포인터 없이 in\-state 저장소에 저장되므로 이 작업을 수행하려면 `v`를 boxing해야 합니다.  Managed Extensions 언어 디자인에서는 암시적 boxing이 지원되지 않으므로 다음과 같이 프로그래머가 이를 명시적으로 지정해야 합니다.  
  
```  
__box( v )->ToString(); // Managed Extensions: note the arrow  
```  
  
 이와 같은 디자인을 채택한 주된 이유는 사용자의 이해를 돕는 데 있습니다. 즉, 프로그래머가 기본 메커니즘을 파악할 수 있도록 함으로써 값 형식 내에 인스턴스를 제공하지 않는 데 따른 '대가'를 이해할 수 있도록 하는 것입니다.  `V`에 `ToString`의 인스턴스가 포함된다면 boxing은 필요하지 않을 것입니다.  
  
 새 구문에서는 개체를 명시적으로 boxing하는 데 따른 어휘의 복잡성이 사라졌지만 boxing 자체로 인한 기본 대가는 제거되지 않았습니다.  
  
```  
v.ToString(); // new syntax  
```  
  
 그러나 어휘의 복잡성이 제거됨으로써 클래스 디자이너는 `V` 내에 `ToString`의 명시적 인스턴스를 제공하지 않는 데 따른 대가와 관련하여 잘못된 판단을 내릴 수도 있습니다.  일반적으로 클래스 디자이너는 한 명이지만 사용자 수는 무제한으로 늘어날 수 있으며 그러한 사용자 중 누구도 성가실 수 있는 명시적 boxing을 제거하기 위해 `V`를 마음대로 수정할 수 없으므로 암시적 boxing을 사용하는 것이 더 좋습니다.  
  
 값 클래스 내에서 `ToString`의 재정의 인스턴스를 제공할지 여부는 그 사용 빈도와 위치를 기준으로 결정해야 합니다.  이를 호출하는 경우가 매우 드물다면 해당 정의에 따른 이점이 거의 없습니다.  마찬가지로, 이를 응용 프로그램의 성능과 관련이 없는 영역에서 호출한다면 이를 추가한다고 해서 응용 프로그램의 전반적인 성능이 향상될 리 없습니다.  대신 boxed 값에 대한 추적 핸들을 유지할 수 있습니다. 이 핸들을 통한 호출에는 boxing이 필요하지 않습니다.  
  
## 값 클래스 기본 생성자 제거  
 Managed Extensions와 새 구문 사이에 발견되는 값 형식의 또 다른 차이는 기본 생성자에 대한 지원이 제거되었다는 사실입니다.  이 생성자를 제거한 이유는 실행 과정에서 관련 기본 생성자를 호출하지 않고 CLR이 값 형식의 인스턴스를 만들 수 있는 경우가 있기 때문입니다.  즉, Managed Extensions로 값 형식 내에서 기본 생성자를 지원하려는 시도는 실제로 그 유효성이 보장되지 않습니다.  그 결과에 대한 아무런 보장이 없으므로 응용 프로그램 내에서 명확하지 않은 상태로 두느니 차라리 이러한 지원을 완전히 삭제하는 것이 더 낫다고 판단했습니다.  
  
 그 결과는 생각만큼 나쁘지 않습니다.  값 형식의 각 개체가 자동으로 0이 되기 때문입니다. 즉, 각 형식이 기본값으로 초기화되기 때문입니다.  따라서 로컬 인스턴스의 멤버는 항상 정의됩니다.  이러한 의미에서 trivial 기본 생성자를 정의하는 기능이 없어도 실제적으로는 해당 기능이 삭제된 것이 전혀 아니며 오히려 CLR에서 작업을 더 효율적으로 수행할 수 있습니다.  
  
 문제는 Managed Extensions의 사용자가 trivial이 아닌 기본 생성자를 정의하는 경우에 있습니다.  새 구문에는 이에 해당하는 내용이 없습니다.  생성자 내의 코드를 명명된 초기화 메서드로 마이그레이션하고 이 메서드를 사용자가 명시적으로 호출해야 합니다.  
  
 이 점을 제외하고 새 구문 내에서 값 형식 개체를 선언하는 방식은 변경되지 않았습니다.  이에 따른 단점으로는 다음과 같은 이유로 인해 값 형식을 네이티브 형식에 대한 래핑에 사용하기가 적절하지 않다는 점을 들 수 있습니다.  
  
-   값 형식 내에서 소멸자를 지원하지 않습니다.  즉, 개체의 수명이 다할 때 트리거되는 일련의 작업을 자동화할 수 없습니다.  
  
-   네이티브 클래스는 관리되는 형식 안에만 포인터로 포함될 수 있고 이는 네이티브 힙에 할당됩니다.  
  
 네이티브 힙에는 네이티브 형식을 저장하고 CLR 힙에는 관리되는 래퍼를 저장하는 방식으로 이중 힙 할당을 피하기 위해 참조 형식 대신 값 형식에 작은 네티이브 클래스를 래핑하려 할 수 있습니다.  값 형식 내에서 네이티브 클래스를 래핑하면 관리되는 힙을 사용하지 않을 수 있지만 네이티브 힙 메모리의 재사용을 자동화할 수 없습니다.  trivial이 아닌 네이티브 클래스를 래핑하는 데 사용할 수 있는 유일한 관리되는 형식은 참조 형식입니다.  
  
## 내부 포인터  
 위의 `Form (2)` 및 `Form (3)`은 관리되는 형식이나 네이티브 형식의 거의 모든 대상을 가리킬 수 있습니다.  따라서 Managed Extensions에서는 다음 예와 같은 구문이 모두 허용됩니다.  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
  
V v = { 0 };  // Form (1)  
V *pv = 0;  // Form (2)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0;  // Form (4)  
  
R* r;  
  
pv = &v;            // address a value type on the stack  
pv = __nogc new V;  // address a value type on native heap  
pv = pvgc;          // we are not sure what this addresses  
pv = pvbx;          // address a boxed value type on managed heap  
pv = &r->vr;        // an interior pointer to value type within a  
                    //    reference type on the managed heap  
```  
  
 `V*`는 로컬 블록 내의 위치를 가리키는 현수 포인터가 될 수도 있고, 전역 범위의 위치를 가리키거나, 네이티브 힙 내의 위치를 가리키거나\(예: 이 포인터가 가리키는 개체가 이미 삭제된 경우\), CLR 힙 내의 위치를 가리켜 가비지 수집 과정에서 재배치해야 하는 경우 추적할 수 있고, 내부 포인터도 자동으로 추적하면서 CLR 힙에 있는 참조 개체의 내부 위치를 가리킬 수 있습니다.  
  
 Managed Extensions에서는 `V*`의 네이티브 측면을 분리할 수 없습니다. 즉, 이는 관리되는 힙에서 개체 또는 하위 개체를 가리킬 수 있는 가능성을 처리하는 포괄적인 측면에서 취급됩니다.  
  
 새 구문의 경우 값 형식 포인터는 두 가지 형식으로 구분됩니다. `V*`는 CLR 이외의 힙 위치로 제한되고, `interior_ptr<V>`는 관리되는 힙 내의 주소를 허용하지만 이를 반드시 필요로 하지는 않는 내부 포인터입니다.  
  
```  
// may not address within managed heap   
V *pv = 0;   
  
// may or may not address within managed heap  
interior_ptr<V> pvgc = nullptr;   
```  
  
 Managed Extensions의 `Form (2)` 및 `Form (3)`은 `interior_ptr<V>`로 매핑됩니다.  `Form (4)`은 추적 핸들입니다.  이는 관리되는 힙 내에서 전체 boxed 개체를 가리킵니다.  새 구문에서 이는 `V^`로 변환됩니다.  
  
```  
V^ pvbx = nullptr; // __box V* pvbx = 0;    
```  
  
 Managed Extensions의 다음과 같은 선언은 모두 새 구문에서 내부 포인터로 매핑됩니다. 이는 `System` 네임스페이스의 값 형식입니다.  
  
```  
Int32 *pi;   // => interior_ptr<Int32> pi;  
Boolean *pb; // => interior_ptr<Boolean> pb;  
E *pe;       // => interior_ptr<E> pe; // Enumeration  
```  
  
 기본 제공 형식은 `System` 네임스페이스에서 형식에 대한 별칭으로 사용되더라도 관리되는 형식으로 간주되지 않습니다.  따라서 Managed Extensions와 새 구문 사이에 다음과 같이 매핑할 수 있습니다.  
  
```  
int * pi;     // => int* pi;  
int __gc * pi2; // => interior_ptr<int> pi2;  
```  
  
 기존 프로그램의 `V*`를 변환할 때 원본을 가장 잘 유지하는 방법은 이를 항상 `interior_ptr<V>`로 변환하는 것입니다.  Managed Extensions에서는 이와 같은 방식으로 처리되었습니다.  새 구문의 경우 프로그래머는 내부 포인터 대신 `V*`를 지정하여 값 형식을 관리되지 않는 힙 주소로 제한할 수 있습니다.  프로그램을 변환할 때 모든 사용을 전이적으로 닫을 수 있고 관리되는 힙에 할당된 주소가 없다는 것이 분명하다면 이를 `V*`로 남겨두는 것이 좋습니다.  
  
## 고정 포인터  
 가비지 수집기는 대개 압축 단계에서 CLR 힙에 있는 개체를 선택에 따라 힙 내의 다른 위치로 옮길 수 있습니다.  추적 핸들, 추적 참조 및 내부 포인터는 이러한 엔터티를 자동으로 업데이트하므로 이러한 이동이 문제가 되지 않습니다.  그러나 사용자가 런타임 환경 외부에서 CLR 힙에 개체의 주소를 전달한 경우 이러한 이동은 문제가 됩니다.  이 경우 개체를 다른 위치로 옮기면 런타임 오류가 발생할 수 있습니다.  이러한 개체가 이동하지 않도록 방지하기 위해서는 이를 외부에서 사용하는 경우에 대비하여 그 위치를 로컬로 고정해야 합니다.  
  
 Managed Extensions에서는 `__pin` 키워드로 포인터 선언을 한정하여 *고정 포인터*를 선언합니다.  다음은 Managed Extensions 선언의 약간 수정된 예제입니다.  
  
```  
__gc struct H { int j; };  
  
int main()   
{  
   H * h = new H;  
   int __pin * k = & h -> j;  
  
   // …  
};  
```  
  
 새 언어 디자인의 경우 고정 포인터는 내부 포인터와 비슷한 구문을 사용하여 선언합니다.  
  
```  
ref struct H  
{  
public:  
   int j;  
};  
  
int main()  
{  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
  
   // …  
}  
```  
  
 새 구문에서 고정 포인터는 특별한 경우의 내부 포인터입니다.  고정 포인터에 대한 기존의 제약 조건은 그대로 적용됩니다.  예를 들어, 고정 포인터는 메서드의 반환 형식이나 매개 변수로 사용할 수 없으며 로컬 개체에서만 선언할 수 있습니다.  그러나 새 구문에는 여러 가지 다른 제약 조건도 더 추가되었습니다.  
  
 고정 포인터의 기본값은 `0`이 아니라 `nullptr`입니다.  `pin_ptr<>`는 `0`으로 초기화하거나 할당할 수 없습니다.  기존 코드에 할당되어 있는 모든 `0`은 `nullptr`로 변경해야 합니다.  
  
 Managed Extensions에서는 고정 포인터를 사용하여 전체 개체를 가리킬 수 있습니다. Managed Extensions 사양의 다음 예제를 참조하십시오.  
  
```  
__gc class G {  
public:  
   void incr(int* pi) { pi += 1; }  
};  
__gc struct H { int j; };  
void f( G * g ) {  
   H __pin * pH = new H;     
   g->incr(& pH -> j);     
};  
```  
  
 새 구문에서는 `new` 식으로 반환된 전체 개체를 고정할 수 없습니다.  대신 내부 멤버의 주소를 고정해야 합니다.  예를 들면 다음과 같습니다.  
  
```  
ref class G {  
public:  
   void incr(int* pi) { *pi += 1; }  
};  
ref struct H { int j; };  
void f( G^ g ) {  
   H ^ph = gcnew H;  
   Console::WriteLine(ph->j);  
   pin_ptr<int> pj = &ph->j;  
   g->incr(  pj );  
   Console::WriteLine(ph->j);  
}  
```  
  
## 참고 항목  
 [값 형식 및 동작\(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)   
 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)