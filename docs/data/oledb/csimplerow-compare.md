---
title: "CSimpleRow::Compare | Microsoft Docs"
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
  - "CSimpleRow.Compare"
  - "CSimpleRow::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare 메서드"
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleRow::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동일한 행 인스턴스를 참조하는지 여부를 확인하기 위해 두 개의 행 을 비교합니다.  
  
## 구문  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### 매개 변수  
 `pRow`  
 `CSimpleRow` 개체에 대한 포인터 입니다.  
  
## 반환 값  
 두 행이 동일한 행임을 나타내는 `S_OK` 또는 두 행이 다른 행임을 나타내는 **S\_FALSE** 인 `HRESULT` 값입니다.  다른 가능한 반환 값은 *OLE DB Programmer's Reference* 의 [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) 를 참조하십시오.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CSimpleRow 클래스](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)