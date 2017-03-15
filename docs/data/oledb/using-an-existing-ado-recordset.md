---
title: "기존 ADO 레코드 집합 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO 레코드 집합[C++]"
  - "OLE DB 소비자 템플릿, ADO 레코드 집합"
  - "레코드 집합[C++], OLE DB에서 사용"
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 기존 ADO 레코드 집합 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB 소비자 템플릿과 ADO\(Active Data Objects\)를 혼합하려면, ADO를 사용하여 OLE DB 소비자 템플릿의 행 집합에 해당하는 레코드 집합을 여십시오.  레코드 집합이 있으면 다음을 수행하여 OLE DB 행 집합에 연결하십시오.  
  
1.  `IRowset` 및 `IAccessor` 포인터에 대해 `QueryInterface`를 호출합니다.  
  
    ```  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *lpUnk*는 ADO 레코드 집합의 **IUnknown** 개체를 가리킵니다.  
  
2.  접근자와 행 집합을 알맞은 OLE DB 소비자 템플릿 클래스에 첨부합니다.  
  
    ```  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)