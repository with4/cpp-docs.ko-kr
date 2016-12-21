---
title: "IRowsetImpl::RestartPosition | Microsoft Docs"
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
  - "ATL.IRowsetImpl.RestartPosition"
  - "IRowsetImpl::RestartPosition"
  - "RestartPosition"
  - "ATL::IRowsetImpl::RestartPosition"
  - "IRowsetImpl.RestartPosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RestartPosition 메서드"
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::RestartPosition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 페치 위치를 초기 위치로 재배치합니다. 즉, 행 집합이 처음 생성되었을 때의 위치입니다.  
  
## 구문  
  
```  
  
      STDMETHOD( RestartPosition )(  
   HCHAPTER /* hReserved */   
);  
```  
  
#### 매개 변수  
 자세한 내용은 *OLE DB Programmer's Reference*에 있는 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)을 참조하십시오.  
  
## 설명  
 열 집합 위치는 **GetNextRow**가 호출될 때까지 정의되지 않습니다.  [RestartPosition](#vcrefirowsetimplrestartposition)를 호출하고 뒤로 페치 또는 스크롤하여 행 집합에서 뒤로 이동할 수 있습니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)