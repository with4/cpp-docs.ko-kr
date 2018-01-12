---
title: "기존 ADO 레코드 집합을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 02f8f29c60601e22a1b005f435d3626336628a1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-existing-ado-recordset"></a>기존 ADO 레코드 집합 사용
OLE DB 소비자 템플릿 및 현재 데이터 개체 (ADO)를 혼합 하려면 ADO를 사용 하 여 레코드 집합 (OLE DB 소비자 템플릿의 행 집합에 해당)을 엽니다. 레코드 집합을 사용 하는 경우에 OLE DB 행 집합에 연결 하려면 다음을 수행 합니다.  
  
1.  호출 `QueryInterface` 에 대 한는 `IRowset` 및 `IAccessor` 포인터입니다.  
  
    ```  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *lpUnk* 가리키는 **IUnknown** ADO 레코드 집합의 개체입니다.  
  
2.  접근자 및 행 집합의 적절 한 OLE DB 소비자 템플릿 클래스에 연결 합니다.  
  
    ```  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)