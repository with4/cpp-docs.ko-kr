---
title: 'Icommandimpl:: Createrowset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateRowset method
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6909f8f6825aacf55c000bfd87e0282365180559
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icommandimplcreaterowset"></a>ICommandImpl::CreateRowset
에 의해 호출 [Execute](../../data/oledb/icommandimpl-execute.md) 단일 행 집합을 만들려고 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      template template <class RowsetClass  
      >  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `RowsetClass`  
 사용자의 행 집합 클래스를 나타내는 템플릿 클래스 멤버입니다. 일반적으로 마법사에서 생성 합니다.  
  
 `pUnkOuter`  
 [in] 제어에 대 한 포인터 **IUnknown** 행 집합의 집계 일부로 만들어지는 경우 인터페이스; 그렇지 않으면 null입니다.  
  
 `riid`  
 [in] 에 해당 `riid` 에서 `ICommand::Execute`합니다.  
  
 `pParams`  
 [/ 출력] 에 해당 `pParams` 에서 `ICommand::Execute`합니다.  
  
 `pcRowsAffected`  
 에 해당 `pcRowsAffected` 에서 `ICommand::Execute`합니다.  
  
 `ppRowset`  
 [/ 출력] 에 해당 `ppRowset` 에서 `ICommand::Execute`합니다.  
  
 `pRowsetObj`  
 [out] 행 집합 개체에 대 한 포인터입니다. 일반적으로이 매개 변수는 사용 되지 않지만 COM 개체를 전달 하기 전에 행 집합에서 더 많은 작업을 수행 해야 하는 경우 사용할 수 있습니다. 수명을 `pRowsetObj` 바인딩된 `ppRowset`합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다. 참조 `ICommand::Execute` 일반 값의 목록에 대 한 합니다.  
  
## <a name="remarks"></a>설명  
 둘 이상의 행 집합을 만드는 또는 서로 다른 행 집합을 만들기 위한 사용자 고유의 조건을 제공 하려면 다른 전화를 걸 `CreateRowset` 내에서 **Execute**합니다.  
  
 참조 [icommand:: Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) 에 *OLE DB 프로그래머 참조 합니다.*  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [ICommandImpl 클래스](../../data/oledb/icommandimpl-class.md)