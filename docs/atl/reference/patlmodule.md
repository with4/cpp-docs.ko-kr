---
title: "_pAtlModule | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATLBASE/_pAtlModule"
  - "_pAtlModule"
  - "ATL::_pAtlModule"
  - "ATL._pAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pAtlModule variable"
  - "pAtlModule variable"
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# _pAtlModule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 모듈에 대 한 포인터를 저장할 전역 변수입니다.  
  
## 구문  
  
```  
__declspec(selectany) CAtlModule * _pAtlModule  
```  
  
## 설명  
 이 전역 변수에서 메서드를 사용 하는 기능을 제공 하는 클래스 \(이전\)  [CComModule](../../atl/reference/ccommodule-class.md) Visual C\+\+ 6.0에서 제공 합니다.  
  
## 예제  
 [!code-cpp[NVC_ATL_Windowing#97](../../atl/codesnippet/CPP/patlmodule_1.cpp)]  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [Global Variables](../../atl/reference/atl-global-variables.md)