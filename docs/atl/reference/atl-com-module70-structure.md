---
title: "_ATL_COM_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::_ATL_COM_MODULE70"
  - "ATL._ATL_COM_MODULE70"
  - "_ATL_COM_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_COM_MODULE70 structure"
  - "ATL_COM_MODULE70 structure"
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
caps.latest.revision: 15
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_COM_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Atl에서 COM 관련 코드 사용  
  
## 구문  
  
```  
  
      struct _ATL_COM_MODULE70{  
   UINT cbSize;  
   HINSTANCE m_hInstTypeLib;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;  
   CRITICAL_SECTION m_csObjMap;  
};  
```  
  
## Members  
 `cbSize`  
 버전 관리에 사용 되는 구조의 크기입니다.  
  
 `m_hInstTypeLib`  
 이 모듈에 대 한 형식 라이브러리 핸들 인스턴스.  
  
 **m\_ppAutoObjMapFirst**  
 이 모듈에 대 한 개체 맵 항목의 시작을 나타내는 배열 요소의 주소입니다.  
  
 **m\_ppAutoObjMapLast**  
 이 모듈에 대 한 개체 맵 항목의 끝을 나타내는 배열 요소의 주소입니다.  
  
 `m_csObjMap`  
 임계 영역 개체 맵 항목에 대 한 액세스를 serialize 합니다.  ATL에서 내부적으로 사용  
  
## 설명  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md) 의 typedef로 정의 된 `_ATL_COM_MODULE70`.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [구조체](../../atl/reference/atl-structures.md)