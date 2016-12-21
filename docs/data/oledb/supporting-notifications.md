---
title: "알림 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이벤트[C++], OLE DB에서 알림"
  - "알림[C++], OLE DB 소비자"
  - "OLE DB 소비자, 알림"
  - "OLE DB 공급자 템플릿, 알림"
  - "OLE DB 공급자, 알림"
  - "행 집합, 이벤트 알림"
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 알림 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## 공급자 및 소비자에 연결 지점 인터페이스 구현  
 알림을 구현하려면 공급자 클래스가 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)와 [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)에서 상속해야 합니다.  
  
 `IRowsetNotifyCP`는 연결 지점 인터페이스 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)에 대한 공급자 사이트를 구현합니다.  `IRowsetNotifyCP`는 연결 지점 **IID\_IRowsetNotify**의 수신자에게 행 집합의 내용에 발생한 변경 내용을 알리기 위한 브로드캐스트 기능을 구현합니다.  
  
 또한 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)을 사용하여 소비자\(싱크\)에 `IRowsetNotify`를 구현하고 등록하여 소비자가 알림을 처리할 수 있도록 해야 합니다.  소비자에 연결 지점 인터페이스를 구현하는 것에 대한 자세한 내용은 [알림 수신](../../data/oledb/receiving-notifications.md)을 참조하십시오.  
  
 뿐만 아니라 클래스에 다음과 같이 연결 지점 항목을 정의하는 맵을 포함해야 합니다.  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## IRowsetNotify 추가  
 `IRowsetNotify`를 추가하려면 상속 체인에 `IConnectionPointContainerImpl<rowset-name>` 및 `IRowsetNotifyCP<rowset-name>`를 추가해야 합니다.  
  
 예를 들어, 다음은 [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f)의 `RUpdateRowset`에 대한 상속 체인입니다.  
  
> [!NOTE]
>  샘플 코드와 여기에 있는 코드가 다르면 샘플 코드가 더 최신 버전입니다.  
  
```  
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan> >, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll > >,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### COM 맵 엔트리 설정  
 또한 행 집합의 COM 맵에 다음을 추가해야 합니다.  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 이러한 매크로는 연결 지점 컨테이너\(`IRowsetNotify`의 기본\)에 `QueryInterface`를 호출하는 사람이 요청한 인터페이스를 공급자에서 찾을 수 있도록 합니다.  연결 지점 사용법에 대한 예제는 ATL POLYGON 샘플과 자습서를 참조하십시오.  
  
### 연결 지점 맵 엔트리 설정  
 연결 지점 맵을 추가해야 합니다.  연결 지점 맵은 다음과 비슷합니다.  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 이 연결 지점 맵은 `IRowsetNotify` 인터페이스를 찾는 구성 요소가 공급자에서 인터페이스를 찾을 수 있도록 합니다.  
  
### 속성 설정  
 공급자에 다음 속성을 추가해야 합니다.  지원하는 인터페이스를 기준으로 속성을 추가하면 됩니다.  
  
|Property|지원할 경우 추가|  
|--------------|---------------|  
|**DBPROP\_IConnectionPointContainer**|항상|  
|**DBPROP\_NOTIFICATIONGRANULARITY**|항상|  
|**DBPROP\_NOTIFICATIONPHASES**|항상|  
|**DBPROP\_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWSETFETCHPOSITIONCHANGE**|항상|  
|**DBPROP\_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWSETRELEASE**|항상|  
|**DBPROP\_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 알림에 대한 대부분의 구현은 OLE DB 공급자 템플릿에 포함되어 있습니다.  상속 체인에 `IRowsetNotifyCP`를 추가하지 않으면 Visual C\+\+ .NET의 컴파일러 기능으로 인해 컴파일러가 컴파일 스트림에서 모든 해당 코드를 제거하므로 코드 크기가 작아집니다.  
  
## 참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)