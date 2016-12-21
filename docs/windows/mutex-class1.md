---
title: "Mutex 클래스 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Mutex 클래스"
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mutex 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

공유 리소스를 단독으로 제어하는 동기화 개체를 나타냅니다.  
  
## 구문  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
  
```  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|**SyncLock**|동기 잠금이 지원되는 클래스에 대한 약어입니다.|  
  
### public 생성자  
  
|Name|설명|  
|----------|--------|  
|[Mutex::Mutex 생성자](../windows/mutex-mutex-constructor.md)|뮤텍스 클래스의 새 인스턴스를 초기화합니다.|  
  
### 공용 멤버  
  
|Name|설명|  
|----------|--------|  
|[Mutex::Lock 메서드](../windows/mutex-lock-method.md)|현재 개체 또는 지정된 핸들과 연결된 뮤텍스개체까지 대기합니다, 뮤텍스를 해제 하거나 지정된 시간 제한 간격이 경과합니다.|  
  
### public 연산자  
  
|Name|설명|  
|----------|--------|  
|[Mutex::operator\= 연산자](../windows/mutex-operator-assign-operator.md)|현재 뮤텍스 개체 할당 \(이동\) 지정한 뮤텍스 개체입니다.|  
  
## 상속 계층  
 `Mutex`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)