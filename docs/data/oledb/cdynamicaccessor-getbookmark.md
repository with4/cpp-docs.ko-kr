---
title: 'Cdynamicaccessor:: Getbookmark | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
dev_langs:
- C++
helpviewer_keywords:
- GetBookmark method
ms.assetid: 6d0a2970-0c62-4a34-bac7-149d8e990f81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac9ea217b987f7355757fc756acc0108fca0e4a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093885"
---
# <a name="cdynamicaccessorgetbookmark"></a>CDynamicAccessor::GetBookmark
현재 행에 대 한 책갈피를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBookmark`  
 [out] 에 대 한 포인터는 [CBookmark](../../data/oledb/cbookmark-class.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
## <a name="remarks"></a>설명  
 로 설정 해야 **DBPROP_IRowsetLocate** 를 `VARIANT_TRUE` 책갈피를 검색할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)