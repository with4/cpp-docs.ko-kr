---
title: 'Icommandimpl:: Execute | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs:
- C++
helpviewer_keywords:
- Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 369c60c1f6407856fb204654794c214fd9ee8b57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
명령을 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Execute(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [icommand:: Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 요청한 송신 인터페이스에는이 함수를 만드는 행 집합 개체에서 가져온 인터페이스가 됩니다.  
  
 **실행** 호출 [CreateRowset](../../data/oledb/icommandimpl-createrowset.md)합니다. 서로 다른 행 집합을 만들기 위한 사용자 고유의 조건을 제공 하거나 둘 이상의 행 집합을 만드는 기본 구현을 재정의 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [ICommandImpl 클래스](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)