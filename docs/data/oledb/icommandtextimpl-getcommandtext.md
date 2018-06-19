---
title: 'Icommandtextimpl:: Getcommandtext | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
dev_langs:
- C++
helpviewer_keywords:
- GetCommandText method
ms.assetid: 0f8da470-b1c3-4573-974f-1acc111e3984
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e2f52f17258e4a317f58e40a60583998673f2efd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101086"
---
# <a name="icommandtextimplgetcommandtext"></a>ICommandTextImpl::GetCommandText
텍스트 명령 집합에 대 한 마지막 호출에서 반환 [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(GetCommandText)(GUID * pguidDialect,   
   LPOLESTR * ppwszCommand);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) 에 *OLE DB Programmer's Reference*합니다. *pguidDialect* 기본적으로 매개 변수가 무시 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [ICommandTextImpl 클래스](../../data/oledb/icommandtextimpl-class.md)