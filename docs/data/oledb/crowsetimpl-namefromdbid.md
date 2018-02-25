---
title: CRowsetImpl::NameFromDBID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
dev_langs:
- C++
helpviewer_keywords:
- NameFromDBID method
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 623eeca73ceaf29e0cecbe80b2a4a8b447adefdc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplnamefromdbid"></a>CRowsetImpl::NameFromDBID
문자열을 추출는 **DBID** 에 복사는 `bstr` 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *pDBID*  
 [in] 에 대 한 포인터는 **DBID** 을 추출할 문자열입니다.  
  
 `bstr`  
 [in] A [CComBSTR](../../atl/reference/ccombstr-class.md) 의 복사본을 배치에 대 한 참조는 **DBID** 문자열입니다.  
  
 `bIndex`  
 [in] **true** 인덱스인 경우 **DBID**; **false** 테이블이 있는 경우 **DBID**합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다. 여부에 따라는 **DBID** 테이블이 나 인덱스 (가리키는 `bIndex`), 메서드 중 하나가 반환 됩니다 **DB_E_NOINDEX** 또는 **DB_E_NOTABLE**합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 `CRowsetImpl` 구현의 [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) 및 [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)