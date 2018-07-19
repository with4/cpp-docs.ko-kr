---
title: 'Iaccessorimpl:: Getbindings | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
dev_langs:
- C++
helpviewer_keywords:
- GetBindings method
ms.assetid: eb550077-77ef-450b-89f1-a2930cee6ab8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e49d1b7b1ff313a1afc89dd39422d50a52342e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099188"
---
# <a name="iaccessorimplgetbindings"></a>IAccessorImpl::GetBindings
접근자에서 소비자에서 기본 열 바인딩을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(GetBindings)(HACCESSOR hAccessor,  
   DBACCESSORFLAGS* pdwAccessorFlags,  
   DBCOUNTITEM* pcBindings,  
   DBBINDING** prgBindings);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IAccessor::GetBindings](https://msdn.microsoft.com/en-us/library/ms721253.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IAccessorImpl 클래스](../../data/oledb/iaccessorimpl-class.md)