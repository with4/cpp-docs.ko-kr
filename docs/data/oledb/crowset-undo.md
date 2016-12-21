---
title: "CRowset::Undo | Microsoft Docs"
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
  - "CRowset.Undo"
  - "ATL::CRowset<TAccessor>::Undo"
  - "CRowset<TAccessor>::Undo"
  - "ATL.CRowset.Undo"
  - "ATL.CRowset<TAccessor>.Undo"
  - "CRowset<TAccessor>.Undo"
  - "ATL::CRowset::Undo"
  - "CRowset::Undo"
  - "Undo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Undo 메서드"
ms.assetid: 1ccd70e2-3931-41c4-893e-a05d0e295410
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Undo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 변화에 대한 실행 취소는 마지막 변경 또는 [Update](../../data/oledb/crowset-update.md) 에 대한 하나의 행에 대해 실행됩니다.  
  
## 구문  
  
```  
  
      HRESULT Undo(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### 매개 변수  
 `pcRows`  
 \[out\] 만일 필요하다면, 실행 취소를 위해 시도된 행의 갯수를 **Undo** 의 위치에 대한 포인터가 반환합니다.  
  
 `phRow`  
 \[out\] 필요하다면 시행취소를 위해 시도된 모든 행에 대한 처리기의 배열을 **Undo** 의 위치에 대한 포인터가 반환합니다.  
  
 `pStatus`  
 \[out\] **Undo** 의 위치에 대한 포인터는 행 상태 값을 반환합니다.  만일 `pStatus` 이 null 이라면 상태 없음이 반환됩니다.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 설명  
 이 메서드에 선택적 인터페이스 `IRowsetUpdate` 를 필요로 하는데, 이것은 모든 공급자들에게 지원되지 않을 수 있습니다; 만일 이경우, 이 메서드는 **E\_NOINTERFACE** 를 반환합니다.  항상 **DBPROP\_IRowsetUpdate** 을 행 집합을 포함하는 명령이나 테이블에서 **Open** 을 호출하기 전에 `VARIANT_TRUE` 로 설정해야합니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)