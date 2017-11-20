---
title: 'Iaccessorimpl:: Getbindings | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
dev_langs: C++
helpviewer_keywords: GetBindings method
ms.assetid: eb550077-77ef-450b-89f1-a2930cee6ab8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 854fda414f7f50860f6458a1ee42911f34d8d53e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="iaccessorimplgetbindings"></a>IAccessorImpl::GetBindings
접근자에서 소비자에서 기본 열 바인딩을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      STDMETHOD(GetBindings)(  
   HACCESSOR hAccessor,  
   DBACCESSORFLAGS* pdwAccessorFlags,  
   DBCOUNTITEM* pcBindings,  
   DBBINDING** prgBindings   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IAccessor::GetBindings](https://msdn.microsoft.com/en-us/library/ms721253.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IAccessorImpl 클래스](../../data/oledb/iaccessorimpl-class.md)