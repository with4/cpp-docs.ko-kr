---
title: 'Crowsetimpl:: M_rgrowdata | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl.m_rgRowData
- CRowsetImpl::m_rgRowData
dev_langs:
- C++
helpviewer_keywords:
- m_rgRowData
ms.assetid: e4e75ca7-12e8-4a0b-94e8-e395c21385b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a83382727c216cfeb9f99a760ee3e755e170ec36
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetimplmrgrowdata"></a>CRowsetImpl::m_rgRowData
기본적으로는 `CAtlArray` 하려면 사용자 레코드 템플릿 인수에 있는 templatizes `CRowsetImpl`합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;  
  
```  
  
## <a name="remarks"></a>설명  
 **ArrayType** 를 템플릿 매개 변수는 `CRowsetImpl`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)   
 [CRowsetImpl::m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)