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
ms.openlocfilehash: d9e1dee5c63281c729cdb798a190938c6433aac0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="receiving-notifications"></a>알림 수신
OLE DB 이벤트가 발생할 때 알림을 수신 하기 위한 인터페이스를 제공 합니다. 에 설명 되어 [OLE DB 개체 알림](https://msdn.microsoft.com/en-us/library/ms725406.aspx) 에 *OLE DB Programmer's Reference*합니다. 이러한 이벤트의 설정은 표준 COM 연결 지점 메커니즘을 사용 합니다. ATL 개체를 통해 이벤트를 검색 하는 예를 들어 `IRowsetNotify` 구현 하는 `IRowsetNotify` 인터페이스를 추가 하 여 `IRowsetNotify` 파생 된 클래스 목록 및를 통해 노출 하는 **COM_INTERFACE_ENTRY** 매크로입니다.  
  
 `IRowsetNotify` 에 다양 한 시간에 호출 될 수 있는 세 가지 메서드가 있습니다. 이러한 메서드 중 하나에 대응 하려는 경우 사용할 수 있습니다는 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 클래스 **E_NOTIMPL** 에 관심이 없는 메서드에 대 한 합니다.  
  
 행 집합을 만들 때 알려야 공급자 지원 하기 위해 반환 된 행 집합 개체를 원하는 **IConnectionPointContainer**, 알림을 설정 하는 데 필요한 합니다.  
  
 다음 코드에서는 ATL 개체에서 행 집합 열기 및 사용 하는 방법을 보여 줍니다.는 `AtlAdvise` 알림 싱크를 설정 하는 함수입니다. `AtlAdvise` 호출할 때 사용 되는 쿠키를 반환 `AtlUnadvise`합니다.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  

product.Open(session, _T("Products"), &propset);  
  

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)