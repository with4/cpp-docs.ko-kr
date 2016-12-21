---
title: "CEnumerator::GetMoniker | Microsoft Docs"
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
  - "GetMoniker"
  - "CEnumerator.GetMoniker"
  - "CEnumerator::GetMoniker"
  - "ATL.CEnumerator.GetMoniker"
  - "ATL::CEnumerator::GetMoniker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMoniker 메서드"
ms.assetid: 69a5cf2d-4a94-41dc-812d-bc1661d516d2
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEnumerator::GetMoniker
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Parses the display name to extract the component of the string that can be converted into a moniker.  
  
## 구문  
  
```  
  
      HRESULT GetMoniker(   
   LPMONIKER* ppMoniker    
) const throw( );  
HRESULT GetMoniker(   
   LPMONIKER* ppMoniker,   
   LPCTSTR lpszDisplayName    
) const throw( );  
```  
  
#### 매개 변수  
 *ppMoniker*  
 \[out\] The moniker parsed from the display name \([CEnumeratorAccessor::m\_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)\) of the current row.  
  
 *lpszDisplayName*  
 \[in\] The display name to parse.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CEnumerator 클래스](../../data/oledb/cenumerator-class.md)