---
title: 'Irowsetupdateimpl:: Update | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
dev_langs:
- C++
helpviewer_keywords:
- Update method
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b398bcc4d522fdb682778de1088c60c5b3ac63f3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetupdateimplupdate"></a>IRowsetUpdateImpl::Update
마지막 페치 또는 업데이트 이후 행에 대해 변경 내용을 전송 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (Update )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hReserved`  
 [in] 에 해당 하는 `hChapter` 매개 변수에서 [irowsetupdate:: Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)합니다.  
  
 다른 매개 변수를 참조 하십시오. [irowsetupdate:: Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 호출 하 여 변경 내용이 전송 [irowsetchangeimpl:: Flushdata](../../data/oledb/irowsetchangeimpl-flushdata.md)합니다. 소비자를 호출 해야 [crowset:: Update](../../data/oledb/crowset-update.md) 변경 내용을 적용 하려면에 대 한 합니다. 설정 *prgRowstatus* 에 설명 된 대로 적절 한 값 [행 상태](https://msdn.microsoft.com/en-us/library/ms722752.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetUpdateImpl 클래스](../../data/oledb/irowsetupdateimpl-class.md)