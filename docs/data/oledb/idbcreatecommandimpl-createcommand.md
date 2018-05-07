---
title: 'Idbcreatecommandimpl:: Createcommand | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
dev_langs:
- C++
helpviewer_keywords:
- CreateCommand method
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 709f734ad0349ea7908466958e282a8ca2a5c2db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="idbcreatecommandimplcreatecommand"></a>IDBCreateCommandImpl::CreateCommand
새 명령을 만들고 요청된 된 인터페이스를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [idbcreatecommand:: Createcommand](https://msdn.microsoft.com/en-us/library/ms709772.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 에 해당 하는 일부 매개 변수 *OLE DB Programmer's Reference* 매개 변수에서 설명 하는 다른 이름의 **idbcreatecommand:: Createcommand**:  
  
|OLE DB 템플릿 매개 변수|*OLE DB Programmer's Reference* 매개 변수|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBCreateCommandImpl 클래스](../../data/oledb/idbcreatecommandimpl-class.md)