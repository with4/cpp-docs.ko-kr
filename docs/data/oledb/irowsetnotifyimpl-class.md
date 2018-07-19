---
title: IRowsetNotifyImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyImpl class
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 860b735863acbcac869a4a297984084946aaf028
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106260"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl 클래스
구현 하 고 등록 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) 소비자 (라고도 "sink")에서 알림을 처리할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[OnFieldChange](../../data/oledb/irowsetnotifyimpl-onfieldchange.md)|열 값의 모든 변경 내용이 소비자를 게 알립니다.|  
|[OnRowChange](../../data/oledb/irowsetnotifyimpl-onrowchange.md)|행의 첫 번째 변경 또는 전체 행에 영향을 주는 변경의 소비자를 게 알립니다.|  
|[OnRowsetChange](../../data/oledb/irowsetnotifyimpl-onrowsetchange.md)|전체 행 집합에 영향을 미치는 변경의 소비자를 게 알립니다.|  
  
## <a name="remarks"></a>설명  
 참조 [알림 수신](../../data/oledb/receiving-notifications.md) 에 소비자 연결 지점 인터페이스를 구현 하는 방법에 대 한 합니다.  
  
 `IRowsetNotifyImpl` 에 대 한 더미 구현을 제공 `IRowsetNotify`에 대 한 빈 함수로 `IRowsetNotify` 메서드 [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx), 및 [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx). 구현 하는 경우이 클래스에서 상속 하는 경우는 `IRowsetNotify` 인터페이스를 해야 하는 메서드만 구현할 수 있습니다. 다른 방법에 대 한 빈 구현을 직접 제공 해야 할 수도 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [IRowsetNotifyCP 클래스](../../data/oledb/irowsetnotifycp-class.md)