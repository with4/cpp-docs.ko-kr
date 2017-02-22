---
title: "방법: shared_ptr 인스턴스 만들기 및 사용 | Microsoft Docs"
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
ms.assetid: 7d6ebb73-fa0d-4b0b-a528-bf05de96518e
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# 방법: shared_ptr 인스턴스 만들기 및 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`shared_ptr` 형식은 메모리에 있는 개체의 수명을 관리하는데 여러 명 있을 경우를 위해 설계 된 C\+\+표준 라이브러리의 스마트 포인터입니다.  `shared_ptr` 를 초기화 한 후에 복사, 함수 인수를 값으로 전달 및 다른 `shared_ptr` 인스턴스로 할당 할 수 있습니다.  모든 인스턴스는 동일한 개체를 가리키고 새 `shared_ptr` 가 추가되거나 범위를 벗어나거나 다시 설정될 때 하나의 "제어 블록"을 공유합니다.  참조 횟수가 0에 도달하면 메모리 자원 및 자체 제어 블록을 삭제 합니다.  
  
 다음 그림에서는 한 메모리 위치를 가리키는 여러 가지 `shared_ptr` 인스턴스를 보여줍니다.  
  
 [![공유 포인터](../cpp/media/shared_ptr.png "shared\_ptr")](assetId:///9785ad08-31d8-411a-86a9-fb9cd9684c27)  
  
## 예제  
 가능하다면 메모리 리소스를 처음으로 만들 때 [make\_shared](../Topic/make_shared%20\(%3Cmemory%3E\).md) 함수를 사용하여 `shared_ptr` 를 만드세요.  `make_shared` 는 예외 안전입니다.  동일한 호출을 사용하여 제어 블록 및 리소스에 대한 메모리를 할당하고 생성 오버 헤드가 줄어듭니다.  만약 `make_shared`을 사용하지 않은 경우 `shared_ptr` 생성자에 전달하기 전에 새 명시적 식에 개체를 만드는 데 사용해야 합니다.  다음 예제에서는 다양한 방법으로 새로운 개체와 함께 선언하고 초기화하는 `shared_ptr` 가 있습니다.  
  
 [!code-cpp[stl_smart_pointers#1](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_1.cpp)]  
  
## 예제  
 다음 예제에서는 이미 할당된 다른 `shared_ptr`하는 개체의 소유권을 공유하는 `shared_ptr` 인스턴스를 어떻게 선언하고 초기화하는지 보여줍니다.  `sp2` 가 초기화된 `shared_ptr`임을 가정하세요.  
  
 [!code-cpp[stl_smart_pointers#2](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_2.cpp)]  
  
## 예제  
 `shared_ptr` 는 표준 템플릿 라이브러리 \(STL\) 컨테이너에 요소를 복사 하는 알고리즘을 사용 하는 경우 또한 도움이 됩니다.  `shared_ptr` 에 요소를 래핑할 수 있고 내부 메모리가 필요할 만큼 유효하고 더 이상인지 아닌지를 이해하면서 다른 컨테이너로 복사 할 수 있습니다.  다음 예제에서는 `shared_ptr` 에 `replace_copy_if` 알고리즘을 만들고 이를 벡터에 사용하는 방법을 보여 줍니다.  
  
 [!code-cpp[stl_smart_pointers#4](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_3.cpp)]  
  
## 예제  
 사용자는 `dynamic_pointer_cast`, `static_pointer_cast` 와 `const_pointer_cast` 을 사용하여 `shared_ptr`을 캐스팅 할 수 있습니다.  이러한 함수는 `dynamic_cast`, `static_cast`, 및 `const_cast` 연산자를 닮습니다.  다음 예제에서는 기본 클래스에서 `shared_ptr` 의 벡터의 각 요소의 파생된 유형을 테스트하는 방법을 보여준 후 클래스의 다음 요소를 복사하고 그에 대한 정보를 표시합니다.  
  
 [!code-cpp[stl_smart_pointers#5](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_4.cpp)]  
  
## 예제  
 `shared_ptr` 를 다음과 같은 방법으로 다른 함수에 전달할 수 있습니다:  
  
-   `shared_ptr` 를 값으로 전달합니다.  이는 복사 생성자를 호출, 참조 횟수를 증가 및 호출 수신자를 소유자로 바꿉니다..  이 작업에 작은 양의 오버 헤드가 있는데 `shared_ptr` 개체를 전달 하는지에 따라 많을 수 있습니다.  호출자와 호출 수신자 사이의 코드 계약 \(암시적 또는 명시적\) 이 호출 수신자가 소유자일 것을 요구할 경우 이 옵션을 사용합니다.  
  
-   참조 또는 const 참조를 통해 `shared_ptr` 를 전달합니다.  이 경우 참조 횟수는 증가하지 않고 호출 수신자는 호출자가 범위를 벗어나지 않는 한 포인터에 액세스할 수 있습니다.  또는 호출 수신자는 참조를 기반으로 `shared_ptr` 를 만들고 공유 소유자가 됩니다.  호출자가 호출 수신자를 모르는 경우 또는 `shared_ptr` 를 전달해야 하고 성능상의 이유로 복사 작업을 하지 않아야 할 경우 이 옵션을 사용합니다.  
  
-   내부 포인터 또는 내부 개체에 대한 참조를 전달합니다.  이 것은 호출 수신자가 개체를 사용하게 하지만 소유권을 공유하거나 수명을 연장 하도록 허용 하지 않습니다.  호출 수신자가 원시 포인터에서 `shared_ptr` 를 생성 하는 경우 새 `shared_ptr` 는 원본에 독립적이 고 내부 리소스를 제어하지 않습니다.  호출자와 호출 수신자 사이의 계약이 명확하게 호출자의 `shared_ptr` 수명에 대한 소유권을 지정 하는 경우 이 옵션을 사용하세요.  
  
-   `shared_ptr`이 어떻게 전달 하는지에 대한 방법을 결정할 때에 호출 수신자가 내부 리소스의 소유권을 공유할 수 있는지 여부를 확인합니다.  "소유자"는 그 것이 필요로 하는 동안의 내부 리소스가 유효한지를 유지하는 개체 또는 함수입니다.  만약 호출자 호출 수신자 이외의 포인터의 해당 수명 \(함수\)의 수명주기를 넘어서 수명을 연장할 수 있음을 보장해야 하는 경우 첫 번째 옵션을 사용합니다.  호출 수신자의 수명 연장 여부를 신경쓰지 않는다면 참조로 전달하고 호출 수신자가 그 것을 복사할 것인지 말 것인지를 결정하게 하세요.  
  
-   도우미 함수 액세스를 내부 포인터로 보내야 하고 도우미 함수가 포인터를 쓰고 호출 함수 이전에 반환하는 것을 알 경우 내부 포인터의 소유권을 공유하지 않아도 됩니다.  호출자의 `shared_ptr` 수명동안 포인터에 액세스 해야 합니다.  이러한 경우 참조에 의해 `shared_ptr` 를 전달하거나 원시 포인터 또는 참조를 내부 개체로 전달하는 것이 안전합니다.  이 이렇게 전달하는 것은 작은 성능 이점을 제공하고 프로그래밍 의도를 표현할 수 있도록 도움이 될 수 있습니다.  
  
-   가끔 `std:vector<shared_ptr<T>>`에 예에서 각각의 `shared_ptr` 를 람다 식 본문 또는 명명된 함수 개체로 전달해야 합니다.  만약 람다 또는 함수가 포인터를 저장 하지 않는 경우 각 요소에 대한 복사 생성자 호출을 피하기 위한 참조에 의해 `shared_ptr` 전달하세요.  
  
 [!CODE [stl_smart_pointers#6](../CodeSnippet/VS_Snippets_Cpp/stl_smart_pointers#6)]  
  
## 예제  
 다음 예제에서는 `shared_ptr` 가 `shared_ptr` 인스턴스가 소유하는 메모리의 포인터 비교를 가능하게 하기 위해 다양한 비교 연산자를 어떻게 오버로드하는지 보여줍니다.  
  
 [!code-cpp[stl_smart_pointers#3](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_6.cpp)]  
  
## 참고 항목  
 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md)