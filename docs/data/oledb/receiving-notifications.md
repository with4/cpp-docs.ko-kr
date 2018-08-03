---
title: 알림 받기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fdef616456b98086bf9490297d68c98596b2dca4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338972"
---
# <a name="receiving-notifications"></a>알림 수신
OLE DB 이벤트가 발생할 때 알림을 수신 하기 위한 인터페이스를 제공 합니다. 에 설명 된 이러한 [OLE DB 개체 알림을](https://msdn.microsoft.com/library/ms725406.aspx) 에 *OLE DB Programmer's Reference*합니다. 표준 COM 연결 지점 메커니즘을 사용 하는 이러한 이벤트를 설치 합니다. ATL 개체를 통해 이벤트를 검색 하려고 하는 예를 들어 `IRowsetNotify` 구현 합니다 `IRowsetNotify` 인터페이스를 추가 하 여 `IRowsetNotify` 파생 된 클래스 목록 및 COM_INTERFACE_ENTRY 매크로 통해 노출 합니다.  
  
 `IRowsetNotify` 에 여러 번 호출할 수 있는 세 가지 메서드가 있습니다. 이러한 메서드 중 하나에 응답 하려는 경우 사용할 수 있습니다 합니다 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 에 관심이 없는 메서드에 대 한 E_NOTIMPL을 반환 하는 클래스입니다.  
  
 행 집합을 만들면 알려야 공급자를 지원 하려면 반환 된 행 집합 개체는 원하는 `IConnectionPointContainer`, 알림을 설정 하는 데 필요한입니다.  
  
 다음 코드에는 ATL 개체에서 행 집합을 열고 사용 하는 방법을 보여 줍니다는 `AtlAdvise` 알림 싱크를 설정 하는 함수입니다. `AtlAdvise` 호출할 때 사용 되는 쿠키를 반환 `AtlUnadvise`합니다.  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)