---
title: 'Irowsetchangeimpl:: Setdata | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SetData
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
dev_langs:
- C++
helpviewer_keywords:
- SetData method
ms.assetid: 81e1dd0a-0518-440c-8808-cee76e4929c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f37ea1e5cbdddf3099356c99acc10014d6ab661f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102214"
---
# <a name="irowsetchangeimplsetdata"></a>IRowsetChangeImpl::SetData
하나 이상의 열에 데이터 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [irowsetchange:: Setdata](https://msdn.microsoft.com/en-us/library/ms721232.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetChangeImpl 클래스](../../data/oledb/irowsetchangeimpl-class.md)