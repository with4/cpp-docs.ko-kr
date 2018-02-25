---
title: 'Crowsetimpl:: Getcommandfromid | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs:
- C++
helpviewer_keywords:
- GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8f58da41c878fba322d51bdecd8283646a94bdf2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplgetcommandfromid"></a>CRowsetImpl::GetCommandFromID
데이터 멤버에 문자열 값을 복사 하는 문자열 값을 포함 하는 매개 변수 중 하나 또는 둘 그리고 있다면 확인 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 및 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,  
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
 이 메서드를 호출 하 여 정적 업캐스팅 통해 `CRowsetImpl` 데이터 멤버를 채우는 데 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 및 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다. 기본적으로이 메서드 중 하나 또는 두 매개 변수 문자열 값을 포함 하는 경우를 확인 합니다. 문자열 값을 포함 하는 경우이 메서드는 문자열 값이 데이터 멤버에 복사 합니다. 이 서명 사용 하 여 메서드를 배치 하 여 프로그램 `CRowsetImpl`-파생 클래스를 기본 구현 하는 대신 메서드를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)