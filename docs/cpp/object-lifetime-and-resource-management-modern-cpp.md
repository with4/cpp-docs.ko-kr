---
title: 개체 수명 및 리소스 관리 (최신 c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 634bef1bf9d2d3128497a1321631ca8665fed144
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423498"
---
# <a name="object-lifetime-and-resource-management-modern-c"></a>개체 수명 및 리소스 관리(최신 C++)
관리 되는 언어와 달리 c + +는 프로그램이 실행 될 때 자동으로 no 긴-사용 되는 메모리 리소스를 해제 하는 가비지 수집 (GC) 되어 있지 않습니다. C + +에서는 리소스 관리 개체 수명 직접 관련 되어 있습니다. 이 문서에서는 c + +에서 개체 수명 및 관리 방법에 영향을 주는 요소에 설명 합니다.  
  
 비 메모리 리소스를 처리 하지 않는 때문에 c + +에서 GC를 갖고 있지 않습니다. 만 c + +에서와 같이 결정적 소멸자 메모리와 비 메모리 리소스를 균등 하 게 처리할 수 있습니다. GC에는 다음과 같은 메모리 및 CPU 사용 및 위치에 더 높은 오버 헤드와 같은 다른 문제가 있습니다. 하지만 보편성은 근본적인 문제 효과적인 최적화를 통해 완화할 수입니다.  
  
## <a name="concepts"></a>개념  
 개체 수명 관리에는 중요 한 것은 캡슐화-리소스 개체를 담당 하는, 또는을 제거 하는 방법을 하거나도 있는지 여부를 소유 하 고 모든 리소스에 알 수 없는 개체를 사용 하는 누구 든 지 합니다. 개체를 소멸만 포함 되어 있습니다. C + + 핵심 언어는 개체 즉, 정확한 시간에 삭제 됩니다 되도록 설계 되었습니다 블록은 종료 반대 순서로 구성 합니다. 개체가 소멸 될 때 기본 항목 및 멤버는 특정 순서로 제거 됩니다.  언어 힙 할당 또는 placement new와 같은 특별 한 작업을 수행 하지 않는 한 자동으로 개체를 제거 합니다.  예를 들어 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md) 같은 `unique_ptr` 및 `shared_ptr`, c + + 표준 라이브러리 컨테이너와 같은 고 `vector`, 캡슐화 `new` / `delete` 및 `new[]` / `delete[]` , 개체의 소멸자가 있습니다. 바로 이러한 이유로 스마트 포인터와 c + + 표준 라이브러리 컨테이너를 사용 하려면 중요 합니다.  
  
 수명 관리의 다른 중요 한 개념: 소멸자입니다. 소멸자는 리소스를 해제할을 캡슐화합니다.  (일반적으로 사용 되는 니모닉 RRID, 리소스 릴리스는 소멸입니다.)  리소스는 "시스템"에서 가져오고 나중에 다시 제공 해야 합니다.  메모리는 가장 일반적인 리소스 하지만 파일, 소켓, 텍스처 및 기타 비 메모리 리소스도 있습니다. 리소스를 "소유" 의미 필요 하지만 함께 완료 되 면 해제 해야 하는 경우 사용할 수 있습니다.  개체가 소멸 될 때 해당 소멸자를 소유 하기는 리소스를 해제 합니다.  
  
 최종 개념은 DAG (방향성 비순환 그래프).  프로그램에서 소유권의 구조는 DAG를 형성합니다. 자체 개체가 소유할 수-없는 불가능 하지만 기본적으로 의미가 없습니다. 하지만 두 개체는 세 번째 개체의 소유권을 공유할 수 있습니다.  다음과 같이 DAG 수는 몇 가지 유형의 링크: A가 B의 구성원이 (B A 소유), C 저장소는 `vector<D>` (C 각 D 요소를 소유), E 저장소는 `shared_ptr<F>` (E 공유 F의 소유권 수 있는 다른 개체와), 등입니다.  없는 사이클은 및에서 DAG의 모든 링크는 개체로 표현 됩니다 (원시 포인터, 핸들 또는 기타 메커니즘) 하는 대신 소멸자가 있는 다음 언어 않고 리소스 누수 가능 하지 않습니다. 리소스는 더 이상 필요하지 없이 가비지 수집기를 실행 한 후에 즉시 해제 됩니다. 추적 수명은 스택 범위, 자료, 멤버 및 관련된 사례에 대 한 오버 헤드 해제 하 고에 대 한 저렴 한 `shared_ptr`합니다.  
  
### <a name="heap-based-lifetime"></a>힙 기반 수명  
 힙 개체 수명에 대 한 사용 하 여 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md)합니다. 사용 하 여 `shared_ptr` 및 `make_shared` 기본 포인터 및 할당자입니다. 사용 하 여 `weak_ptr` 를 끊어 주기, 캐싱, 수행에 영향을 주거나 수명에 대해 가정 하지 않고 개체를 관찰 합니다.  
  
```cpp  
void func() {  
  
auto p = make_shared<widget>(); // no leak, and exception safe  
...  
p->draw();   
  
} // no delete required, out-of-scope triggers smart pointer destructor  
  
```  
  
 사용 하 여 `unique_ptr` 고유 소유권에 대 한 예는 *pimpl* 관용구 합니다. (참조 [컴파일 타임 캡슐화에 대 한 Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md).) 확인 된 `unique_ptr` 모두 명시적의 기본 대상 `new` 식입니다.  
  
```cpp  
unique_ptr<widget> p(new widget());  
```  
  
 소유권과 관찰에 대 한 원시 포인터를 사용할 수 있습니다. 비 소유 포인터 dangle 수 있지만 누출 수 없습니다.  
  
```cpp  
class node {  
  ...  
  vector<unique_ptr<node>> children; // node owns children  
  node* parent; // node observes parent, which is not a concern  
  ...  
};  
node::node() : parent(...) { children.emplace_back(new node(...) ); }  
  
```  
  
 사용 하도록 할 수 성능 최적화에 필요한 경우 *잘 캡슐화 된* 포인터 및 삭제에 대 한 명시적 호출을 소유 합니다. 예에는 자체 하위 수준의 데이터 구조를 구현 하는 경우입니다.  
  
### <a name="stack-based-lifetime"></a>스택 기반 수명  
 현대적인 c + + *스택 기반 범위* 자동 조합 하기 때문에 강력한 코드를 작성 하는 강력한 방법이 *스택 수명* 및 *데이터 멤버 수명* 고효율와- 추적 수명은 기본적으로 오버 헤드의 무료입니다. 힙 개체 수명 효과적인 수동 관리 걸리며 원시 포인터를 사용 하는 경우에 특히 원본 리소스 누수 및 비효율적인, 될 수 있습니다. 스택 기반 범위를 보여 주는이 코드를 살펴보세요.  
  
```cpp  
class widget {  
private:  
    gadget g;   // lifetime automatically tied to enclosing object  
public:  
    void draw();  
};  
  
void functionUsingWidget () {  
    widget w;   // lifetime automatically tied to enclosing scope  
                // constructs w, including the w.g gadget member  
    // ...
    w.draw();  
    // ...
} // automatic destruction and deallocation for w and w.g  
  // automatic exception safety,   
  // as if "finally { w.dispose(); w.g.dispose(); }"  
```  
  
 정적 수명을 가급적 사용 하지 않습니다 (전역 정적, 로컬 정적 함수) 하므로 문제가 발생할 수 있습니다. 전역 개체의 생성자는 예외를 throw 하는 경우 어떻게 되나요? 일반적으로 응용 프로그램 오류를 디버그 하기 어려울 수 있는 방식으로 합니다. 생성 순서는 정적 수명 개체에 대 한 문제가 및 동시성 안전 하지 않습니다. 뿐만 아니라 개체 생성을은 문제가 다형성이 포함 되는 경우에 특히 소멸 순서 복잡할 수 있습니다. 개체 또는 변수가 다형 아니고 없는 복잡 한 생성/소멸 순서, 경우에 사업이 여전히 스레드로부터 안전한 동시성 문제가 있습니다. 안전 하 게는 다중 스레드 응용 프로그램 스레드 로컬 저장소, 리소스 잠금 및 다른 특별 한 주의 필요 없이 정적 개체의 데이터를 수정할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)