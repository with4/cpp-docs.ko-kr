---
title: 알림 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f750346b0fdd8821800b012b3cdff7acc12f7897
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112097"
---
# <a name="supporting-notifications"></a>알림 지원
## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>공급자 및 소비자 연결 지점 인터페이스 구현  
 상속 해야 합니다는 공급자 클래스를 구현 하기 위해 알림 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) 및 [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)합니다.  
  
 `IRowsetNotifyCP` 연결 지점 인터페이스에 대 한 공급자 사이트 구현 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)합니다. `IRowsetNotifyCP` 구현 브로드캐스트 수신기 연결 지점에 대해 알리기 위해 함수 **IID_IRowsetNotify** 행 집합의 내용 변경 합니다.  
  
 또한 구현 하 고 등록 해야 하는 참고 `IRowsetNotify` (싱크 라고도 함)를 사용 하 여 소비자에 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 소비자 알림을 처리할 수 있도록 합니다. 소비자에 연결 지점 인터페이스를 구현 하는 방법에 대 한 정보를 참조 하십시오. [알림 수신](../../data/oledb/receiving-notifications.md)합니다.  
  
 또한 클래스 다음과 같이 연결 지점 항목을 정의 하는 맵을 포함 되어 있어야 합니다.  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>IRowsetNotify 추가  
 추가 하려면 `IRowsetNotify`에 추가 해야 `IConnectionPointContainerImpl<rowset-name>` 및 `IRowsetNotifyCP<rowset-name>` 상속 체인으로 연결 합니다.  
  
 상속 체인을 예를 들어, 다음은 `RUpdateRowset` 에 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  샘플 코드는 여기 표시 된 것과 다를 수 있습니다. 샘플 코드를 보다 최신 버전으로 간주 해야 합니다.  
  
```cpp
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan>>, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll >>,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### <a name="setting-com-map-entries"></a>COM 맵 엔트리를 설정합니다.  
 다음 행 집합의 COM 맵의을 추가 해야 합니다.  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 두이 매크로 호출 하는 모든 사용 `QueryInterface` 연결 지점 컨테이너에 대 한 (의 기본 `IRowsetNotify`) 공급자의 요청된 된 인터페이스를 찾을 수 있습니다. 연결점을 사용 하는 방법의 예로 ATL 다각형 샘플 및 자습서를 참조 하십시오.  
  
### <a name="setting-connection-point-map-entries"></a>연결 지점 맵 엔트리를 설정합니다.  
 연결 지점 맵을 추가 해야 합니다. 다음과 같이 같아야 합니다.  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 이 연결 지점 맵은 수에 대 한 원하는 구성 요소는 `IRowsetNotify` 인터페이스 공급자에서 찾을 수 있습니다.  
  
### <a name="setting-properties"></a>속성 설정  
 공급자에는 다음 속성을 추가 해야 합니다. 사용자가 지 원하는 인터페이스를 기반으로 하는 속성을 추가 하기만 하면 됩니다.  
  
|속성|지원할 경우 추가|  
|--------------|------------------------|  
|**DBPROP_IConnectionPointContainer**|Always|  
|**DBPROP_NOTIFICATIONGRANULARITY**|Always|  
|**DBPROP_NOTIFICATIONPHASES**|Always|  
|**DBPROP_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE**|Always|  
|**DBPROP_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWSETRELEASE**|Always|  
|**DBPROP_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 대부분의 구현 된 알림에 대 한 OLE DB 공급자 템플릿에 이미 포함 되어 있습니다. 추가 하지 않으면 `IRowsetNotifyCP` 상속 체인에 위해 컴파일러 프로그램 컴파일 스트림에서 코드 크기가 더 작은 하는 모든 코드를 제거 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)