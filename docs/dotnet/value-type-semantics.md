---
title: "값 형식 의미 체계 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- interior_ptr keyword [C++]
- virtual functions, value types
- inheritance, value types
- pinning pointers
- pin_ptr keyword [C++]
- __pin keyword
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 21a7d6bcba2fca3fddd6f5e234663d6791398f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="value-type-semantics"></a>값 형식 의미
값 형식 의미 체계 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 다음은 c + + 사양에 대 한 관리 되는 확장에 사용 되는 간단한 정식 값 형식입니다.  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
```  
  
 Managed Extensions (여기서 forms 2와 3 단계는 동일 의미 체계가) 값 형식의 네 가지 구문 변형이 있을 수 있습니다 있습니다.  
  
```  
V v = { 0 };       // Form (1)  
V *pv = 0;         // Form (2) an implicit form of (3)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0; // Form (4) must be local   
```  
  
## <a name="invoking-inherited-virtual-methods"></a>상속 된 가상 메서드를 호출합니다.  
 `Form (1)`정식 값 개체 이며 같은 상속된 된 가상 메서드를 호출 하려고 할 때 사용자를 제외 하 고 잘 파악 하기 `ToString()`합니다. 예:  
  
```  
v.ToString(); // error!  
```  
  
 재정의 되지 않은 때문에이 메서드를 호출 하려면 `V`, 컴파일러는 기본 클래스의 관련된 가상 테이블에 대 한 액세스 해야 합니다. 값 형식에서 상태 저장소 없이 가상 테이블 (vptr)에 연결 된 포인터 이기 때문에이 실행 하려면 `v` boxed 수 있습니다. Managed Extensions 언어 디자인 암시적 boxing은 지원 되지 않지만 명시적으로 지정 해야에서 프로그래머가  
  
```  
__box( v )->ToString(); // Managed Extensions: note the arrow  
```  
  
 이 설계는 주요 이유는 채택한: 그녀는 이해 ' 그녀의 값 형식 내에서 인스턴스를 제공 하지 않도록 프로그래머에 게 표시 되도록 해야 기본 메커니즘입니다. 된 `V` 의 인스턴스를 포함 하도록 `ToString`, boxing 필요 하지 않을 것입니다.  
  
 하지만 boxing 자체에 대 한 기본 비용 하지를 명시적으로 boxing 어휘 복잡성 새 구문에서 제거 됩니다.  
  
```  
v.ToString(); // new syntax  
```  
  
 커밋되지만의 명시적 인스턴스를 제공 하지 않는 데의 비용에 대 한 클래스 디자이너는 잘못 되었을 수는 `ToString` 메서드 내에서 `V`합니다. 암시적 boxing 원인은 하나만 클래스 디자이너는 일반적으로,는 수정할 수 있을 누구도 사용자의 무제한 `V` 가능 성가실 명시적 상자 제거 합니다.  
  
 재정의 인스턴스 제공 여부를 결정 하는 기준은 `ToString` 내 값의 빈도 그 사용 위치 클래스 여야 합니다. 거의 호출 되 면 것은 물론 거의 의미가 정의 합니다. 마찬가지로, 응용 프로그램의 성능이 아닌 영역에서 호출 되 면 것 추가 하면 추가 해 서 응용 프로그램의 전반적인 성능이 합니다. 또는 추적 핸들 boxed 값을 유지할 수 있습니다 하 고 해당 핸들을 통해 호출 boxing 필요 하지 않습니다.  
  
## <a name="there-is-no-longer-a-value-class-default-constructor"></a>값 클래스 기본 생성자는 더 이상  
 또 다른 차이점 값 형식과 함께 관리 하는 확장 및 새 구문 기본 생성자에 대 한 지원 제거 하는 것입니다. 연결 된 기본 생성자를 호출 하지 않고 CLR 값 형식의 인스턴스를 만들 수 있는 실행 하는 동안 경우가 있기 때문입니다. 즉, 값 형식 내에서 기본 생성자를 지원 하기 위해 Managed extensions 시도 수 연습에 없는 않을 수 있습니다. 응용 프로그램에서 명확 하 게 하는 것이 아니라 지지도 완전히 삭제 하는 더 나은 것으로 판단 되었습니다 보장이 제공 합니다.  
  
 처음 까다롭습니다 나쁘지 않습니다. 즉, 각 개체는 값 형식의 자동으로 제거 됩니다 (각 종류를 기본값으로 초기화 됩니다.). 결과적으로, 로컬 인스턴스 멤버는 항상 정의 합니다. 전반에 trivial 기본 생성자를 정의 하는 기능 손실 실제로 손실 전혀-이며 실제로 CLR에서 수행 될 때 더 효율적입니다.  
  
 Managed extensions 사용자는 특수 한 기본 생성자를 정의 하는 경우입니다. 이 새 구문에 대 한 매핑이 없습니다. 생성자 내에서 코드는 다음 사용자가 명시적으로 호출 하는 명명 된 초기화 방법으로 마이그레이션할 수 있도록 해야 합니다.  
  
 그렇지 않으면 새 구문 내에서 값 형식 개체의 선언을 변경 되지 않습니다. 아래쪽 옆의 값 형식은 표시 되는 하지 네이티브 형식의 래핑 만족 스러운 이유는 다음과 같습니다.  
  
-   값 형식 내에서 소멸자에 대 한 지원은 없습니다. 즉, 개체의 수명의 끝에 의해 트리거되는 작업 집합을 자동화 하 방식은 없습니다.  
  
-   다음으로 할당 되는 네이티브 힙에 대 한 포인터로 관리 되는 형식 내 에서만 네이티브 클래스를 포함할 수 있습니다.  
  
 값 형식 보다는 참조 형식이 double 힙 할당을 방지 하기 위해에서 작은 네이티브 클래스 래핑 싶습니다: 네이티브 형식을 보유할 네이티브 힙과 관리 되는 래퍼를 보유 하는 CLR 힙으로부터 합니다. 값 형식 내에서 네이티브 클래스 래핑 관리 되는 힙 피할 수 있습니다 하지만 네이티브 힙 메모리의 재사용을 자동화할 수 없으므로 제공 합니다. 참조 유형은 특정 기본 클래스를 래핑하는 관리 되는 유일한 형식입니다.  
  
## <a name="interior-pointers"></a>내부 포인터  
 `Form (2)`및 `Form (3)` 위에 해결할 수 거의 모든 항목에이 world] 또는 [다음 (즉, 모든 관리 또는 네이티브). 따라서 예를 들어 관리 되는 확장에서 다음 작업을 모두 허용 됩니다.  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
  
V v = { 0 };  // Form (1)  
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
  
 따라서 한 `V*` 로컬 블록 내에 있는 위치를 처리할 수 있습니다 (및 따라서 수 현 수 참조일), 네이티브 내에서 전역 범위에서 CLR 힙에 (예를 들어 자신이 처리 하는 개체는 이미 삭제 된 경우), 힙 (및 따라서를 추적 해야 하는 경우 위치를 변경 하는 동안 가비지 수집), 및 CLR 힙으로부터 (내부 포인터,이 호출할 때은 또한 투명 하 게 추적)에서 참조 방식 개체를 내부에 있습니다.  
  
 Managed extensions에서는의 기본 요소를 분리할 수 없으므로 `V*`; 즉, 처리 됩니다는 포괄적인 측면에서 개체 또는 관리 되는 힙에 대 한 하위 개체의 가능성은 처리 합니다.  
  
 새 구문에서는 값 형식 포인터는 두 가지 유형으로 포함: `V*`는 비-CLR 힙 위치 및 내부 포인터 제한 됩니다 `interior_ptr<V>`에 대 한 수는 있지만 관리 되는 힙 내의 주소 필요 하지 않습니다.  
  
```  
// may not address within managed heap   
V *pv = 0;   
  
// may or may not address within managed heap  
interior_ptr<V> pvgc = nullptr;   
```  
  
 `Form (2)`및 `Form (3)` Managed extensions를 매핑할 `interior_ptr<V>`합니다. `Form (4)`추적 핸들이입니다. 관리 되는 힙 내 boxed 전체 개체를 해결 합니다. 에 새 구문에서 변환 되는 `V^`,  
  
```  
V^ pvbx = nullptr; // __box V* pvbx = 0;    
```  
  
 다음 선언을 Managed extensions 새 구문에서 내부 포인터에 매핑됩니다. (내에서 값 형식에서 `System` 네임 스페이스입니다.)  
  
```  
Int32 *pi;   // => interior_ptr<Int32> pi;  
Boolean *pb; // => interior_ptr<Boolean> pb;  
E *pe;       // => interior_ptr<E> pe; // Enumeration  
```  
  
 기본 제공 형식에서 형식에 대 한 별칭으로 사용 되더라도 관리 되는 형식 간주 되지 않습니다는 `System` 네임 스페이스입니다. 따라서 다음 매핑을 유지 관리 되는 확장 및 새 구문 사이 참이:  
  
```  
int * pi;     // => int* pi;  
int __gc * pi2; // => interior_ptr<int> pi2;  
```  
  
 변환할 때는 `V*` 가장 보수적인 전략은 기존 프로그램에 항상 상태로 전환 하는 `interior_ptr<V>`합니다. Managed extensions 처리 되었음을 방법입니다. 새 구문에서 프로그래머는 관리 되지 않는 힙 주소 지정 하 여 값 형식을 제한할 수 `V*` 내부 포인터 대신 합니다. 프로그램을 변환할 때에 모든 사용의 전이적 closure를 수행 하 고 관리 되는 힙에 할당 된 주소가 것 수, 있으면 남겨 두는 것으로 `V*` 괜찮습니다.  
  
## <a name="pinning-pointers"></a>포인터 고정  
 가비지 수집기는 압축 단계 일반적으로 힙 내의 다른 위치로 CLR 힙에 있는 개체를 이동할 필요에 따라 수 있습니다. 이 이동 핸들, 추적 참조 및 내부 포인터 이러한 엔터티를 투명 하 게 업데이트를 추적 하는 문제가 되지 않습니다. 그러나 문제를 사용자가 개체의 주소 런타임 환경 외부에서 CLR 힙에 쳤으 면은 이러한 이동. 이 경우 개체의 위치로 옮기면은 런타임 오류가 발생할 수 있습니다. 이동, 목록과 해당 사용법은 외부 범위에 대 한 위치에 로컬로 고정 해야에서는 이러한 개체를 제외 합니다.  
  
 Managed extensions에서는 *고정 포인터* 포인터 선언을 정규화 하 여 선언 된 `__pin` 키워드입니다. Managed Extensions 사양에서 약간 수정 하는 예제는 다음과 같습니다.  
  
```  
__gc struct H { int j; };  
  
int main()   
{  
   H * h = new H;  
   int __pin * k = & h -> j;  
  
   // ...  
};  
```  
  
 새 언어 디자인 내부 포인터와 비슷한 구문을 사용 하 여 고정 포인터를 선언 합니다.  
  
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
  
   // ...  
}  
```  
  
 새 구문에서 고정 포인터는 내부 포인터의 특별 한 경우. 고정 포인터에 대 한 원래 제약 조건이 유지 됩니다. 매개 변수로 사용할 수 없습니다 또는; 메서드의 반환 형식이 예를 들어 로컬 개체에 대해서만 선언할 수 있습니다. 그러나 새 구문에서 추가 되었습니다 다양 한 추가 제약 조건.  
  
 고정 포인터의 기본값은 `nullptr`이 아니라 `0`합니다. A `pin_ptr<>` 초기화 하거나 할당할 수 없습니다 `0`합니다. 모든 할당 `0` 기존 코드의으로 변경 해야 합니다 `nullptr`합니다.  
  
 Managed extensions 고정 포인터 Managed Extensions 사양에서 가져온 다음 예제와 같이 전체 개체를 해결 하기 위해 수 있었습니다.  
  
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
  
 새 구문에서 전체 개체를 고정 반환한는 `new` 식은 지원 되지 않습니다. 대신, 내부 멤버의 주소를 고정 해야 합니다. 예를 들어 개체에 적용된  
  
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
  
## <a name="see-also"></a>참고 항목  
 [값 형식 및 동작 (C + + /cli CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)   
 [interior_ptr (C + + /cli CLI)](../windows/interior-ptr-cpp-cli.md)   
 [pin_ptr(C++/CLI)](../windows/pin-ptr-cpp-cli.md)