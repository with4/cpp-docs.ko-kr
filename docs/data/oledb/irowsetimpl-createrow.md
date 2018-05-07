---
title: 'Irowsetimpl:: Createrow | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs:
- C++
helpviewer_keywords:
- CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eae3fbdce1db5760d4ee5ca75e007c01e98b7bed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
호출 하는 도우미 메서드입니다 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) 할당할 새 **HROW**합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *lRowsOffset*  
 만들고 있는 행의 커서 위치입니다.  
  
 *cRowsObtained*  
 대 한 참조가 생성 된 행의 수를 나타내는 사용자에 게 다시 전달 합니다.  
  
 *rgRows*  
 배열을 **HROW**s 새로 만든된 행 핸들을 사용 하 여 호출자에 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출 하는 행이 있으면 [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) 를 반환 합니다. 그렇지 않으면, RowClass 템플릿 변수의 새 인스턴스를 할당를에 추가 [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)