---
title: 'Irowsetcreatorimpl:: Setsite | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
dev_langs: C++
helpviewer_keywords: SetSite method
ms.assetid: e92e63d5-93e4-4ee0-9ef7-bb6583cc8091
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed3f5f0bce2408cd2a4439aac6728f0e00760b1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetcreatorimplsetsite"></a>IRowsetCreatorImpl::SetSite
행 집합 개체를 포함 하는 사이트를 설정 합니다. 자세한 내용은 참조 [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      STDMETHOD( SetSite )(  
   IUnknown* pCreator   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCreator`  
 [in] 에 대 한 포인터는 **IUnknown** 행 집합 개체를 관리 하는 사이트의 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 또한 `IRowsetCreatorImpl::SetSite` OLE DB를 사용 하면 **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS** 속성입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetCreatorImpl 클래스](../../data/oledb/irowsetcreatorimpl-class.md)