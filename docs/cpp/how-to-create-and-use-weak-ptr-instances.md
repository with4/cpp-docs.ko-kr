---
title: "방법: weak_ptr 인스턴스 만들기 및 사용 | Microsoft Docs"
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
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: weak_ptr 인스턴스 만들기 및 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일부 경우에는 개체가 참조 수를 늘리지 않고 `shared_ptr`의 기본 개체에 액세스하는 방법이 있어야 합니다.  일반적으로 `shared_ptr` 인스턴스 사이에 순환 참조가 있는 경우 발생하는 상황입니다.  
  
 가능할 때마다 포인터의 공유 소유권을 회피하는 디자인이 가장 좋습니다.  그러나 `shared_ptr` 인스턴스 소유권을 공유해야 하는 경우에는 그 사이에 순환 참조를 사용하지 마십시오.  순환 참조를 피할 수 없거나 어떤 이유로 더 적합할 경우 `weak_ptr`를 사용하여 하나 이상의 소유자에게 다른 `shared_ptr`에 대한 약한 참조를 제공합니다.  `weak_ptr`을 사용하여 기본 메모리 리소스가 아직 유효할 경우에만 기존의 관련 인스턴스 집합에 조인하는 `shared_ptr`을 만들 수 있습니다.  `weak_ptr` 자체는 참수 수 계산에 참가하지 않으므로 참조 수가 0이 되는 것을 방지할 수 없습니다.  그러나 `weak_ptr`을 사용하여 함께 초기화된 `shared_ptr`의 새 복사본을 얻으려고 시도할 수 있습니다.  메모리가 이미 삭제된 경우 **bad\_weak\_ptr** 예외가 throw 됩니다.  메모리가 계속 유효한 경우 새 공유 포인터가 참조 개수를 증분하고 `shared_ptr` 변수가 범위 내에 있는 동안 메모리가 유효함을 보장합니다.  
  
## 예제  
 다음 코드 예제는 `weak_ptr`이 순환 종속성이 있는 개체의 적절한 삭제를 확인 하는 데 사용되는 경우를 보여줍니다.  예제를 자세히 보면서 대체 솔루션을 고려한 후에만 생성된 것으로 가정하십시오.  `Controller` 개체는 컴퓨터 프로세스의 일부 측면을 나타내며 독립적으로 운영됩니다.  각 컨트롤러는 언제든지 다른 컨트롤러의 상태를 쿼리할 수 있지만 각 컨트롤러에는 이 용도의 전용 `vector<weak_ptr<Controller>>`가 있습니다.  각 벡터는 회전 참조를 포함하므로 `shared_ptr` 대신 `weak_ptr` 인스턴스가 사용됩니다.  
  
 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  
  
  **컨트롤러0 만들기**  
**컨트롤러1 만들기**  
**컨트롤러2 만들기**  
**컨트롤러3 만들기**  
**컨트롤러4 만들기**  
**push\_back to v\[0\]: 1**  
**push\_back to v\[0\]: 2**  
**push\_back to v\[0\]: 3**  
**push\_back to v\[0\]: 4**  
**push\_back to v\[1\]: 0**  
**push\_back to v\[1\]: 2**  
**push\_back to v\[1\]: 3**  
**push\_back to v\[1\]: 4**  
**push\_back to v\[2\]: 0**  
**push\_back to v\[2\]: 1**  
**push\_back to v\[2\]: 3**  
**push\_back to v\[2\]: 4**  
**push\_back to v\[3\]: 0**  
**push\_back to v\[3\]: 1**  
**push\_back to v\[3\]: 2**  
**push\_back to v\[3\]: 4**  
**push\_back to v\[4\]: 0**  
**push\_back to v\[4\]: 1**  
**push\_back to v\[4\]: 2**  
**push\_back to v\[4\]: 3**  
**use\_count \= 1**  
**1의 상태 \= 설정**  
**2의 상태 \= On**  
**3의 상태 \= On**  
**4의 상태 \= On**  
**use\_count \= 1**  
**0의 상태 \= On**  
**2의 상태 \= On**  
**3의 상태 \= On**  
**4의 상태 \= On**  
**use\_count \= 1**  
**0의 상태 \= On**  
**1의 상태 \= 설정**  
**3의 상태 \= On**  
**4의 상태 \= On**  
**use\_count \= 1**  
**0의 상태 \= On**  
**1의 상태 \= 설정**  
**2의 상태 \= On**  
**4의 상태 \= On**  
**use\_count \= 1**  
**0의 상태 \= On**  
**1의 상태 \= 설정**  
**2의 상태 \= On**  
**3의 상태 \= On**  
**Controller0 삭제**  
**Controller1 삭제**  
**Controller2 삭제**  
**Controller3 삭제**  
**Controller4 삭제**  
**아무 키를 누르십시오.** 시험 삼아 `vector<shared_ptr<Controller>>`가 될 벡터 `others`를 수정하면 출력에서 `TestRun`이 반환될 때 소멸자는 호출되지 않습니다.  
  
## 참고 항목  
 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md)