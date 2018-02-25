---
title: 'Icommandtextimpl:: Getcommandtext | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5da83e0be8b15c317e9bf97d2f11acc3d7f85e2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
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