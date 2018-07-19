---
title: 'Irowsetimpl:: M_breset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
dev_langs:
- C++
helpviewer_keywords:
- m_bReset
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9aec38e3cf7e9a58c4fe99d06f35ae55cfdf81c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102009"
---
# <a name="irowsetimplmbreset"></a>IRowsetImpl::m_bReset
행 집합에서 커서 위치를 정의할 경우 결정 하는 데 사용 되는 비트 플래그입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
unsigned m_bReset:1;  
  
```  
  
## <a name="remarks"></a>설명  
 소비자를 호출 하는 경우 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) 는 음수와 `lOffset` 또는 *cRows* 및 `m_bReset` 가 true 이면 `GetNextRows` 행 집합의 끝으로 이동 합니다. 경우 `m_bReset` false 이면 소비자는 OLE DB 사양에서 오류 코드가 수신 됩니다. `m_bReset` 로 플래그 설정 가져옵니다 **true** 행 집합을 처음으로 만들어질 및 소비자 호출 하는 경우 [irowsetimpl:: Restartposition](../../data/oledb/irowsetimpl-restartposition.md)합니다. 로 설정 됩니다 **false** 호출 하는 경우 `GetNextRows`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)