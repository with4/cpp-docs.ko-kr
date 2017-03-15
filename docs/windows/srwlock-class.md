---
title: "SRWLock 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLock 클래스"
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# SRWLock 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

슬림 판독기\/기록기 잠금을 나타냅니다.  
  
## 구문  
  
```  
class SRWLock;  
```  
  
## 설명  
 슬림 판독기\/기록기 잠금 개체 또는 리소스에 스레드 간의 액세스를 동기화하는 데 사용 됩니다.  자세한 내용은 런타임 라이브러리에서 [함수 동기화](http://msdn.microsoft.com/ko-kr/9b6359c2-0113-49b6-83d0-316ad95aba1b) 를 참조하십시오.  
  
## 멤버  
  
### 공용 Typedefs  
  
|||  
|-|-|  
|**SyncLockExclusive**|단독 모드에서 획득 하는 SRWLock 개체에 대한 약어입니다.|  
|**SyncLockShared**|공유 모드에서 획득 하는 SRWLock 개체에 대한 약어입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[SRWLock::SRWLock 생성자](../windows/srwlock-srwlock-constructor.md)|SRWLock 클래스의 새 인스턴스를 초기화합니다.|  
|[SRWLock::~SRWLock 소멸자](../windows/srwlock-tilde-srwlock-destructor.md)|SRWLock 클래스의 인스턴스를 초기화하지 않습니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[SRWLock::LockExclusive 메서드](../windows/srwlock-lockexclusive-method.md)|단독 모드에서 SRWLock 개체를 가져옵니다.|  
|[SRWLock::LockShared 메서드](../windows/srwlock-lockshared-method.md)|공유 모드에서 SRWLock 개체를 가져옵니다.|  
|[SRWLock::TryLockExclusive 메서드](../windows/srwlock-trylockexclusive-method.md)|현재 또는 지정 된 SRWLock 개체에 대 한 단독 사용 모드로 SRWLock 개체를 얻으려고 합니다.|  
|[SRWLock::TryLockShared 메서드](../windows/srwlock-trylockshared-method.md)|현재 또는 지정 된 SRWLock 개체에 대한 공유 사용 모드로 SRWLock 개체를 얻으려고 합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[SRWLock::SRWLock\_ 데이터 멤버](../windows/srwlock-srwlock-data-member.md)|현재 SRWLock 개체에 대한 내부 잠금을 변수를 포함합니다.|  
  
## 상속 계층  
 `SRWLock`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)