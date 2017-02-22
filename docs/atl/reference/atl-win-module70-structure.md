---
title: "_ATL_WIN_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_WIN_MODULE70"
  - "ATL::_ATL_WIN_MODULE70"
  - "ATL._ATL_WIN_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_WIN_MODULE70 structure"
  - "ATL_WIN_MODULE70 structure"
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _ATL_WIN_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Atl에서 창 작업 코드 사용  
  
## 구문  
  
```  
  
      struct _ATL_WIN_MODULE70{  
   UNIT cbSize;  
   CRITICAL_SECTION m_csWindowCreate;  
   _AtlCreateWndData* m_pCreateWndList;  
   CSimpleArray<ATOM> m_rgWindowClassAtoms;  
};  
```  
  
## Members  
 `cbSize`  
 버전 관리에 사용 되는 구조의 크기입니다.  
  
 `m_csWindowCreate`  
 등록 코드 창에 대 한 액세스를 serialize 하는 데 사용 합니다.  ATL에서 내부적으로 사용  
  
 **m\_pCreateWndList**  
 Windows 해당 개체에 바인딩하는 데 사용 합니다.  ATL에서 내부적으로 사용  
  
 **m\_rgWindowClassAtoms**  
 종료 시 제대로 등록 되지 수 있도록 창 클래스 등록을 추적 하는 데 사용 합니다.  ATL에서 내부적으로 사용  
  
## 설명  
 [\_ATL\_WIN\_MODULE](../Topic/_ATL_WIN_MODULE.md) 의 typedef로 정의 된 `_ATL_WIN_MODULE70`.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [구조체](../../atl/reference/atl-structures.md)