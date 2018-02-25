---
title: 'Crowsetimpl:: Setcommandtext | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
dev_langs:
- C++
helpviewer_keywords:
- SetCommandText method
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e345799f74d4c32ffae88baebb69ed828266dcfc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplsetcommandtext"></a>CRowsetImpl::SetCommandText
유효성을 검사 하 고 저장 된 **DBID**두 문자열의 s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 및 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pTableID`  
 [in] 에 대 한 포인터는 **DBID** 나타내는 테이블 id입니다.  
  
 `pIndexID`  
 [in] 에 대 한 포인터는 **DBID** 나타내는 인덱스 id입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 **SetCommentText** 메서드는 `CreateRowset`, 정적 메서드를 처리할 `IOpenRowsetImpl`합니다.  
  
 이 메서드를 호출 하 여 해당 작업을 위임 [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) 및 [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) 캐스팅 되지 않은 포인터를 통해.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)