---
title: "Semaphore 클래스 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Semaphore 클래스"
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Semaphore 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제한된 수의 사용자를 지원할 수 있는 공유 리소스를 제어하는 동기화 개체를 나타냅니다.  
  
## 구문  
  
```  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`SyncLock`|동기 잠금이 지원되는 클래스에 대한 약어입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[Semaphore::Semaphore 생성자](../windows/semaphore-semaphore-constructor.md)|세마포 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[InvokeHelper::Invoke 메서드](../windows/invokehelper-invoke-method.md)|지정한 개수의 인수를 포함하는 시그니처를 가진 이벤트 처리기를 호출 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[Semaphore::Lock 메서드](../windows/semaphore-lock-method.md)|현재 개체 또는 지정된 핸들과 연결된 개체까지 대기 신호를 받은 상태 이거나 지정된 시간 제한 간격이 경과합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[Semaphore::operator\= 연산자](../windows/semaphore-operator-assign-operator.md)|현재 세마포 개체를 세마포 개체에서 지정된 된 핸들로 이동합니다.|  
  
## 상속 계층  
 `Semaphore`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)