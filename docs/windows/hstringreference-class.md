---
title: "HStringReference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HStringReference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기존 문자열에서 생성된 HSTRING을 나타냅니다.  
  
## 구문  
  
```cpp  
class HStringReference;  
```  
  
## 설명  
 새 HSTRING의 백업 버퍼의 수명은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]가 관리하지 않습니다.  호출자는 힙 할당을 피하고 메모리 누수의 위험을 제거하기 위해 스택 프레임에 소스 문자열을 할당합니다.  또한 호출자는 연결된 HSTRING의 수명 동안 소스 문자열이 변경되지 않는지 확인해야 합니다.  자세한 내용은 [WindowsCreateStringReference function](http://msdn.microsoft.com/ko-kr/0361bb7e-da49-4289-a93e-de7aab8712ac)을 참조하십시오.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[HStringReference::HStringReference 생성자](../windows/hstringreference-hstringreference-constructor.md)|HStringReference 클래스의 새 인스턴스를 초기화합니다.|  
  
### 멤버  
  
|멤버|설명|  
|--------|--------|  
|[HStringReference::CopyTo 메서드](../windows/hstringreference-copyto-method.md)|현재 HStringReference 개체를 HSTRING 개체로 복사합니다.|  
|[HStringReference::Get 메서드](../windows/hstringreference-get-method.md)|기본 HSTRING 핸들의 값을 검색합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[HStringReference::Operator\= 연산자](../windows/hstringreference-operator-assign-operator.md)|다른 HStringReference 개체의 값을 현재 HStringReference 개체로 이동합니다.|  
|[HStringReference::Operator\=\= 연산자](../windows/hstringreference-operator-equality-operator.md)|두 매개 변수가 같은지 여부를 나타냅니다.|  
|[HStringReference::Operator\!\= 연산자](../windows/hstringreference-operator-inequality-operator.md)|두 매개 변수가 같지 않은지 여부를 나타냅니다.|  
  
## 상속 계층  
 `HStringReference`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)