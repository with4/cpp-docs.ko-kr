---
title: 'Irowsetinfoimpl:: Getreferencedrowset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
dev_langs:
- C++
helpviewer_keywords:
- GetReferencedRowset method
ms.assetid: 94d2155c-9da0-4c19-a37c-bc35716359fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ca538822acdc9493e89639715588db35d5cee686
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetinfoimplgetreferencedrowset"></a>IRowsetInfoImpl::GetReferencedRowset
책갈피 적용 되는 행 집합에 대 한 인터페이스 포인터를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,  
   REFIID riid,  
   IUnknown** ppReferencedRowset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IRowsetInfo::GetReferencedRowset](https://msdn.microsoft.com/en-us/library/ms721145.aspx) 에 *OLE DB Programmer's Reference*합니다. *iOrdinal* 매개 변수는 책갈피 열 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetInfoImpl 클래스](../../data/oledb/irowsetinfoimpl-class.md)   
 [IRowsetInfoImpl::GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)