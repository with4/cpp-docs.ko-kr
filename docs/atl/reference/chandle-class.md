---
title: "CHandle Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CHandle"
  - "ATL::CHandle"
  - "CHandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHandle class"
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CHandle Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 만들고 핸들 개체를 사용 하는 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
class CHandle  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHandle::CHandle](../Topic/CHandle::CHandle.md)|생성자입니다.|  
|[CHandle::~CHandle](../Topic/CHandle::~CHandle.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHandle::Attach](../Topic/CHandle::Attach.md)|이 메서드를 호출 하는 `CHandle` 개체에 기존 핸들.|  
|[CHandle::Close](../Topic/CHandle::Close.md)|종료 하려면이 메서드를 호출 하는 `CHandle` 개체입니다.|  
|[CHandle::Detach](../Topic/CHandle::Detach.md)|핸들에서 분리 하는이 메서드를 호출 하는 `CHandle` 개체입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CHandle::operator HANDLE](../Topic/CHandle::operator%20HANDLE.md)|저장 된 핸들 값을 반환합니다.|  
|[CHandle::operator \=](../Topic/CHandle::operator%20=.md)|할당 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CHandle::m\_h](../Topic/CHandle::m_h.md)|핸들을 저장 하는 멤버 변수입니다.|  
  
## 설명  
 A `CHandle` 개체에 대 한 핸들을 필요할 때마다 사용할 수 있습니다: 주요 차이점은 `CHandle` 개체가 자동으로 삭제 됩니다.  
  
> [!NOTE]
>  다른 INVALID\_HANDLE\_VALUE를 사용 하는 동안 일부 API 함수는 비어 있거나 잘못 된 핸들로 NULL을 사용 합니다.  `CHandle`사용 하며 NULL INVALID\_HANDLE\_VALUE 실제 핸들로 처리합니다.  INVALID\_HANDLE\_VALUE를 반환 하는 API를 호출 하면 호출 하기 전에이 값을 확인 해야  [CHandle::Attach](../Topic/CHandle::Attach.md) 또는 전달 하는 `CHandle` 생성자 대신 NULL을 전달 하 고.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)