---
title: 'Ierrorrecordsimpl:: Getcustomerrorobject | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
dev_langs:
- C++
helpviewer_keywords:
- GetCustomErrorObject method
ms.assetid: 96d3549b-a49c-4552-94b2-71babaf1bf20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b89955ed3dbb11e4bb310b44526d390d6c143fc1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100248"
---
# <a name="ierrorrecordsimplgetcustomerrorobject"></a>IErrorRecordsImpl::GetCustomErrorObject
사용자 지정 오류 개체에는 인터페이스에 대 한 포인터를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)