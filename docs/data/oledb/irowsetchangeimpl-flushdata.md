---
title: 'Irowsetchangeimpl:: Flushdata | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
dev_langs: C++
helpviewer_keywords: FlushData method
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 31555e1f8305a281955902b71fdc71fbcc5405e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetchangeimplflushdata"></a>IRowsetChangeImpl::FlushData
데이터 저장소에 커밋하는 공급자에 의해 재정의 되 면입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *hRowToFlush*  
 [in] 데이터에 대 한 행에 대 한 핸들입니다. 이 행의 형식이 결정 됩니다는 *RowClass* 의 템플릿 인수는 `IRowsetImpl` 클래스 (`CSimpleRow` 기본적으로).  
  
 *hAccessorToFlush*  
 [in] 바인딩 정보 및에서 유형 정보를 포함 하는 접근자에 대 한 핸들의 **PROVIDER_MAP** (참조 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetChangeImpl 클래스](../../data/oledb/irowsetchangeimpl-class.md)