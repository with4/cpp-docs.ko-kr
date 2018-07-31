---
title: IDBCreateSessionImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 756cc7ba203a1655bf5112d9c03e84707644f1e5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337572"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl 클래스
에 대 한 구현을 제공 합니다 [IDBCreateSession](https://msdn.microsoft.com/library/ms724076.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 파생 된 클래스  
  
 *SessionClass*  
 세션 개체입니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h 
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[CreateSession](#createsession)|데이터 원본 개체에서 새 세션을 만들고 새로 만들어진된 세션에서 요청된 된 인터페이스를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 데이터 원본 개체에는 필수 인터페이스입니다.  

## <a name="createsession"></a> Idbcreatesessionimpl:: Createsession
데이터 원본 개체에서 새 세션을 만들고 새로 만들어진된 세션에서 요청된 된 인터페이스를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [idbcreatesession:: Createsession](https://msdn.microsoft.com/library/ms714942.aspx) 에 *OLE DB Programmer's Reference*합니다.   
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)