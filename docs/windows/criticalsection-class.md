---
title: "CriticalSection 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSection 클래스"
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSection 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

임계 영역 개체를 나타냅니다.  
  
## 구문  
  
```  
class CriticalSection;  
```  
  
## 멤버  
  
### 생성자  
  
|Name|설명|  
|----------|--------|  
|[CriticalSection::CriticalSection 생성자](../windows/criticalsection-criticalsection-constructor.md)|뮤텍스 개체와 유사하지만 단일 프로세스에서 스레드에서 사용할 수 있는 동기화 개체를 초기화 합니다.|  
|[CriticalSection::~CriticalSection 소멸자](../windows/criticalsection-tilde-criticalsection-destructor.md)|현재 CriticalSection 개체를 초기화하지 않고 삭제합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CriticalSection::TryLock 메서드](../windows/criticalsection-trylock-method.md)|차단하지 않고 중요 섹션에 진입하려고 시도합니다.  호출이 성공한 경우, 호출 스레드는 중요 섹션의 소유권을 갖습니다.|  
|[CriticalSection::Lock 메서드](../windows/criticalsection-lock-method.md)|지정된 임계 영역 개체를 소유할 때까지 기다립니다.  호출 스레드가 소유권을 부여하는 경우 함수를 반환 합니다.|  
|[CriticalSection::IsValid 메서드](../windows/criticalsection-isvalid-method.md)|임계 현재 유효한지 여부를 나타냅니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CriticalSection::cs\_ 데이터 멤버](../windows/criticalsection-cs-data-member.md)|중요 섹션에 대한 데이터 멤버를 선언합니다.|  
  
## 상속 계층  
 `CriticalSection`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)