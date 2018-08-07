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
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a20be1a92c93be38d901f58339bb02b24cf2661f
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339957"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl 클래스
구현 및 등록 [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx) 소비자 (라고도 "sink")에 알림을 처리할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[OnFieldChange](#onfieldchange)|열의 값을 변경한의 소비자를 게 알립니다.|  
|[OnRowChange](#onrowchange)|첫 번째 행을 변경 또는 전체 행에 영향을 주는 변경 소비자를 게 알립니다.|  
|[OnRowsetChange](#onrowsetchange)|전체 행 집합에 영향을 미치는 변경의 소비자를 게 알립니다.|  
  
## <a name="remarks"></a>설명  
 참조 [알림 수신](../../data/oledb/receiving-notifications.md) 에서 소비자 연결 지점 인터페이스를 구현 하는 방법에 대 한 합니다.  
  
 `IRowsetNotifyImpl` 더미 구현을 제공 `IRowsetNotify`에 대 한 빈 함수를 사용 하 여 합니다 `IRowsetNotify` 메서드 [OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx)에 [OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx), 및 [OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx). 구현 하는 경우이 클래스에서 상속 하는 경우는 `IRowsetNotify` 인터페이스를 해야 하는 방법만 구현할 수 있습니다. 다른 방법에 대 한 빈 구현을 직접 제공 해야 합니다.  

## <a name="onfieldchange"></a> Irowsetnotifyimpl:: Onfieldchange
열의 값을 변경한의 소비자를 게 알립니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(OnFieldChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ HROW /* hRow */,  
/* [in] */ DBORDINAL /* cColumns */,  
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) 매개 변수 설명에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 참조 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) 에 대 한 설명 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 래핑하는 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) 메서드. 자세한 내용은 OLE DB 프로그래머 참조에서 해당 메서드의 설명을 참조하십시오.  

## <a name="onrowchange"></a> Irowsetnotifyimpl:: Onrowchange
첫 번째 행을 변경 또는 전체 행에 영향을 주는 변경 소비자를 게 알립니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(OnRowChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBCOUNTITEM /* cRows */,  
/* [size_is][in] */ const HROW /* rghRows*/ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [irowsetnotify:: Onrowchange](https://msdn.microsoft.com/library/ms722694.aspx) 매개 변수 설명에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 참조 [irowsetnotify:: Onrowchange](https://msdn.microsoft.com/library/ms722694.aspx) 에 대 한 설명 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 래핑하는 [irowsetnotify:: Onrowchange](https://msdn.microsoft.com/library/ms722694.aspx) 메서드. 자세한 내용은 OLE DB 프로그래머 참조에서 해당 메서드의 설명을 참조하십시오. 

## <a name="onrowsetchange"></a> Irowsetnotifyimpl:: Onrowsetchange
전체 행 집합에 영향을 미치는 변경의 소비자를 게 알립니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(OnRowsetChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) 매개 변수 설명에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 참조 [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) 에 대 한 설명 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 래핑하는 [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) 메서드. 자세한 내용은 OLE DB 프로그래머 참조에서 해당 메서드의 설명을 참조하십시오.
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx)   
 [IRowsetNotifyCP 클래스](../../data/oledb/irowsetnotifycp-class.md)