---
title: "CRowset::MoveNext | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.MoveNext"
  - "ATL.CRowset.MoveNext"
  - "ATL::CRowset<TAccessor>::MoveNext"
  - "CRowset<TAccessor>.MoveNext"
  - "CRowset.MoveNext"
  - "CRowset<TAccessor>::MoveNext"
  - "CRowset::MoveNext"
  - "ATL::CRowset::MoveNext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveNext 메서드"
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::MoveNext
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

커서를 다음 레코드로 이동합니다.  
  
## 구문  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
```  
  
#### 매개 변수  
 `lSkip`  
 \[in\] 가져오기 전에 건너뛸 열의 수입니다.  
  
 `bForward`  
 \[in\] 다음 레코드의 앞으로 이동시키기 위해서는 **true**를 전달하고, 뒤로 이동시키기 위해서는 **false**를 전달합니다.  
  
## 반환 값  
 표준 `HRESULT`입니다.  열 집합의 끝에 도달했을 때, **DB\_S\_ENDOFROWSET**을 반환합니다.  
  
## 설명  
 이전 위치를 기억하여 `CRowset` 개체로부터 다음 순차적인 열을 가져옵니다.  사용자는 마음대로 `lSkip`열의 앞을 건너뛰거나 뒤로 이동하는 것을 선택할 수 있습니다.  
  
 이 방법은 표 또는 열 집합을 포함하는 명령에서 **Open**을 호출하기 전에 다음 속성을 설정하는 것을 요구합니다.  
  
-   `lSkip` \< 0 이면, **DBPROP\_CANSCROLLBACKWARDS**는 `VARIANT_TRUE`이 되어야 합니다.  
  
-   `bForward` \= false인 경우, **DBPROP\_CANFETCHBACKWARDS**은 `VARIANT_TRUE`이 되어야 합니다.  
  
 그렇지 않으면, \(만약 `lSkip` \>\=0 이고 `bForward` \= true\), 사용자는 어떤 추가 속성도 설정할 필요가 없습니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)