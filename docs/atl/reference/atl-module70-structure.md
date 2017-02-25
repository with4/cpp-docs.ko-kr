---
title: "_ATL_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_MODULE70"
  - "ATL::_ATL_MODULE70"
  - "ATL._ATL_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MODULE70 structure"
  - "ATL_MODULE70 structure"
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# _ATL_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 ATL 모듈에 의해 사용 되는 데이터를 포함 합니다.  
  
## 구문  
  
```  
  
      struct _ATL_MODULE70{  
   UINT cbSize;  
   LONG m_nLockCnt;  
   _ATL_TERMFUNC_ELEM* m_pTermFuncs;  
   CComCriticalSection m_csStaticDataInitAndTypeInfo;  
};  
```  
  
## Members  
 `cbSize`  
 버전 관리에 사용 되는 구조의 크기입니다.  
  
 `m_nLockCnt`  
 참조 횟수를 모듈 살아 남아 있어야 기간 결정 합니다.  
  
 **m\_pTermFuncs**  
 등록 된 ATL을 종료할 때 호출할 함수를 트랙.  
  
 **m\_csStaticDataInitAndTypeInfo**  
 다중 스레드 환경에서 내부 데이터에 대 한 액세스를 조정 하는 데 사용 합니다.  
  
## 설명  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md) 의 typedef로 정의 된 `_ATL_MODULE70`.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [구조체](../../atl/reference/atl-structures.md)