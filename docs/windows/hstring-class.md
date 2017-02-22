---
title: "HString 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString"
dev_langs: 
  - "C++"
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HString 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HSTRING 핸들 조작에 대한 지원울 제공합니다.  
  
## 구문  
  
```cpp  
class HString;  
```  
  
## 설명  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]는 HSTRING 핸들을 통해 문자열에 대한 액세스를 제공합니다.  HString 클래스는 편의 함수 및 연산자를 제공하여 HSTRING 핸들을 사용을 단순화합니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[HString::HString 생성자](../windows/hstring-hstring-constructor.md)|HString 클래스의 새 인스턴스를 초기화합니다.|  
|[HString::~HString 소멸자](../windows/hstring-tilde-hstring-destructor.md)|HString 클래스의 현재 인스턴스를 제거합니다.|  
  
### 멤버  
  
|Name|설명|  
|----------|--------|  
|[HString::Set 메서드](../windows/hstring-set-method.md)|현재 HString 개체의 값을 지정된 와이드 문자 문자열 또는 HString 매개 변수로 설정합니다.|  
|[HString::Attach 메서드](../windows/hstring-attach-method.md)|지정된 HString 개체와 현재 HString 개체를 연결합니다.|  
|[HString::CopyTo 메서드](../windows/hstring-copyto-method.md)|현재 HString 개체를 HSTRING 개체로 복사합니다.|  
|[HString::Detach 메서드](../windows/hstring-detach-method.md)|지정된 HString 개체를 기본 값에서 해제합니다.|  
|[HString::GetAddressOf 메서드](../windows/hstring-getaddressof-method.md)|기본 HSTRING 핸들에 대한 포인터를 검색합니다.|  
|[HString::Get 메서드](../windows/hstring-get-method.md)|기본 HSTRING 핸들의 값을 검색합니다.|  
|[HString::Release 메서드](../windows/hstring-release-method.md)|기본 문자열 값을 삭제하고 현재 HString 개체를 빈 값으로 초기화합니다.|  
|[HString::MakeReference 메서드](../windows/hstring-makereference-method.md)|지정된 문자열 매개 변수에서 HStringReference 개체를 만듭니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[HString::Operator\= 연산자](../windows/hstring-operator-assign-operator.md)|다른 HString 개체의 값을 현재 HString 개체로 이동합니다.|  
|[HString::Operator\=\= 연산자](../windows/hstring-operator-equality-operator.md)|두 매개 변수가 같은지 여부를 나타냅니다.|  
|[HString::Operator\!\= 연산자](../windows/hstring-operator-inequality-operator.md)|두 매개 변수가 같지 않은지 여부를 나타냅니다.|  
  
## 상속 계층  
 `HString`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)