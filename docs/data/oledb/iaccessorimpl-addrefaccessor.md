---
title: 'Iaccessorimpl:: Addrefaccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
dev_langs: C++
helpviewer_keywords: AddRefAccessor method
ms.assetid: 4c15392c-944b-4cbd-8cc7-2a5c2f308a70
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 39f40ce476b457d6e8f0b7d6e9333a8b96ef0afc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="iaccessorimpladdrefaccessor"></a>IAccessorImpl::AddRefAccessor
기존 접근자에 대 한 참조 횟수를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      STDMETHOD(AddRefAccessor)(  
   HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IAccessor::AddRefAccessor](https://msdn.microsoft.com/en-us/library/ms714978.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IAccessorImpl 클래스](../../data/oledb/iaccessorimpl-class.md)   
 [Iaccessorimpl:: Createaccessor](../../data/oledb/iaccessorimpl-createaccessor.md)   
 [IAccessorImpl::ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)