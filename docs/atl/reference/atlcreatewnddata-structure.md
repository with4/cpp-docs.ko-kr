---
title: "_AtlCreateWndData Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::_AtlCreateWndData"
  - "ATL._AtlCreateWndData"
  - "_AtlCreateWndData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AtlCreateWndData structure"
  - "AtlCreateWndData structure"
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _AtlCreateWndData Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 구조는 atl에서 창 작업 코드에서 클래스 인스턴스 데이터 포함  
  
## 구문  
  
```  
  
      struct _AtlCreateWndData{  
   void* m_pThis;  
   DWORD m_dwThreadID;  
   _AtlCreateWndData* m_pNext;  
};  
```  
  
## Members  
 **m\_pThis**  
 **이** 포인터에 창 프로시저에 액세스 하려면 클래스의 인스턴스를 사용 합니다.  
  
 `m_dwThreadID`  
 클래스 인스턴스의 현재 스레드 ID입니다.  
  
 **m\_pNext**  
 다음 포인터 `_AtlCreateWndData` 개체입니다.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [구조체](../../atl/reference/atl-structures.md)