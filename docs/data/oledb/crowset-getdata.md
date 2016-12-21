---
title: "CRowset::GetData | Microsoft Docs"
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
  - "CRowset<TAccessor>::GetData"
  - "ATL::CRowset<TAccessor>::GetData"
  - "ATL::CRowset::GetData"
  - "ATL.CRowset<TAccessor>.GetData"
  - "CRowset<TAccessor>.GetData"
  - "CRowset::GetData"
  - "CRowset.GetData"
  - "ATL.CRowset.GetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetData 메서드[OLE DB]"
ms.assetid: 1e0347b5-3e24-4ff8-a790-839616c1522f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::GetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

행 집합의 행 복사본에서 데이터를 검색합니다.  
  
## 구문  
  
```  
  
      HRESULT GetData( ) throw( );   
HRESULT GetData(   
   int nAccessor    
) throw( );  
```  
  
#### 매개 변수  
 `nAccessor`  
 \[in\] 데이터 액세스를 사용하기 위한 접근자의 인덱스번호\(0\-오프셋\)입니다.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 설명  
 만일 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) 에서 자동 접근자가 아닌 접근자를 지정하는 경우, 접근자 번호를 전달함으로써 데이터를 명시적으로 얻기위한 이 메서드를 사용합니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)