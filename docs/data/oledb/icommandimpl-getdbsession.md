---
title: 'Icommandimpl:: Getdbsession | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
dev_langs:
- C++
helpviewer_keywords:
- GetDBSession method
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 116838ebb5857d5761b9d58d4f84e315de56d240
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099747"
---
# <a name="icommandimplgetdbsession"></a>ICommandImpl::GetDBSession
명령을 만든 세션에 대 한 인터페이스 포인터를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (GetDBSession) (REFIID riid,  
   IUnknown** ppSession);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 세션에서 속성을 검색 하는 데 유용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [ICommandImpl 클래스](../../data/oledb/icommandimpl-class.md)