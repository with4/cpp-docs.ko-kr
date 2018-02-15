---
title: "IRowsetNotifyCP 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetNotifyCP
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyCP class
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d20a4eb011b67a743e91f1f8340c80ea146bb7c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP 클래스
연결 지점 인터페이스에 대 한 공급자 사이트 구현 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)합니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray>,  
   public ReentrantEventSync  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 `IRowsetNotifyCP`합니다.  
  
 `ReentrantEventSync`  
 재입력을 지 원하는 mutex 클래스 (기본값은 **CComSharedMutex**). 뮤텍스는 한 스레드가 리소스에 상호 배타적 액세스 허용 하는 동기화 개체입니다.  
  
 `piid`  
 인터페이스 ID 포인터 (**IID\***)에 대 한 프로그램 **IRowsetNotify** 연결 지점 인터페이스입니다. 기본값은 **& __uuidof(IRowsetNotify)**합니다.  
  
 `DynamicUnkArray`  
 형식의 배열 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), 되는 동적으로 할당 된 배열을 **IUnknown** 클라이언트에 대 한 포인터 싱크 인터페이스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[Fire_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|열 값에 대 한 변경의 소비자를 게 알립니다.|  
|[Fire_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|행에 영향을 미치는 변경의 소비자를 게 알립니다.|  
|[Fire_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|전체 행 집합에 영향을 미치는 변경의 소비자를 게 알립니다.|  
  
## <a name="remarks"></a>설명  
 `IRowsetNotifyCP` 구현 브로드캐스트 수신기 연결 지점에 대해 알리기 위해 함수 **IID_IRowsetNotify** 행 집합의 내용 변경 합니다.  
  
 또한 구현 하 고 등록 해야 하는 참고 `IRowsetNotify` (라고도 "sink")를 사용 하 여 소비자에 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 소비자 알림을 처리할 수 있도록 합니다. 참조 [알림 수신](../../data/oledb/receiving-notifications.md) 에 소비자 연결 지점 인터페이스를 구현 하는 방법에 대 한 합니다.  
  
 알림을 구현에 대 한 자세한 내용은의 "알림 지원" 참조 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [알림 (COM)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)