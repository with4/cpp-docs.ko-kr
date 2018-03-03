---
title: "CHandle 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
dev_langs:
- C++
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd58ba8ce15bb26b4e5b768baedbf8ddfe829f2b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="chandle-class"></a>CHandle 클래스
이 클래스를 만들고 개체 핸들을 사용 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CHandle
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|생성자입니다.|  
|[CHandle:: ~ CHandle](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|연결 하려면이 메서드를 호출 하는 `CHandle` 개체 기존 핸들입니다.|  
|[CHandle::Close](#close)|이 메서드를 닫습니다는 `CHandle` 개체입니다.|  
|[CHandle::Detach](#detach)|핸들을 분리 하려면이 메서드를 호출 하는 `CHandle` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CHandle::operator 핸들](#operator_handle)|저장 된 핸들의 값을 반환합니다.|  
|[CHandle::operator =](#operator_eq)|대입 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|핸들을 저장 하는 멤버 변수입니다.|  
  
## <a name="remarks"></a>설명  
 A `CHandle` 개체 핸들을이 필요할 때마다 사용할 수 있습니다: 주요 차이점은는 `CHandle` 개체가 자동으로 삭제 됩니다.  
  
> [!NOTE]
>  INVALID_HANDLE_VALUE 사용 하 고 다른 일부 API 함수는 비어 있거나 잘못 된 핸들으로 NULL을 사용 합니다. `CHandle`만 사용 하 여 NULL 및 실제 핸들 INVALID_HANDLE_VALUE 취급합니다. 호출 하기 전에이 값을 확인 해야 INVALID_HANDLE_VALUE를 반환할 수 있는 API를 호출 하면 [CHandle::Attach](#attach) 또는 전달 하는 `CHandle` 생성자를 대신 NULL을 전달 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="attach"></a>CHandle::Attach  
 연결 하려면이 메서드를 호출 하는 `CHandle` 개체 기존 핸들입니다.  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `h`  
 `CHandle`핸들의 소유권을 갖게 됩니다 `h`합니다.  
  
### <a name="remarks"></a>설명  
 할당의 `CHandle` 개체는 `h` 처리 합니다. 디버그 빌드에서 ATLASSERT 발생 합니다 `h` 은 NULL입니다. 다른 검사가 핸들의 유효성이 수행 되지 않습니다.  
  
##  <a name="chandle"></a>CHandle::CHandle  
 생성자입니다.  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `h`  
 기존 핸들 또는 `CHandle`합니다.  
  
### <a name="remarks"></a>설명  
 새 `CHandle` 개체, 필요에 따라 기존 핸들을 사용 하 여 또는 `CHandle` 개체입니다.  
  
##  <a name="dtor"></a>CHandle:: ~ CHandle  
 소멸자입니다.  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>설명  
 해제 된 `CHandle` 호출 하 여 개체 [CHandle::Close](#close)합니다.  
  
##  <a name="close"></a>CHandle::Close  
 이 메서드를 닫습니다는 `CHandle` 개체입니다.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>설명  
 열려 있는 개체 핸들을 닫습니다. 핸들은 NULL 이며이 경우 될 경우 **닫기** 가 이미 호출는 ATLASSERT 발생 디버그 빌드에서 합니다.  
  
##  <a name="detach"></a>CHandle::Detach  
 핸들을 분리 하려면이 메서드를 호출 하는 `CHandle` 개체입니다.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 분리 되 고 핸들을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 핸들의 소유권을 해제합니다.  
  
##  <a name="m_h"></a>CHandle::m_h  
 핸들을 저장 하는 멤버 변수입니다.  
  
```
HANDLE m_h;
```  
  
##  <a name="operator_eq"></a>CHandle::operator =  
 대입 연산자입니다.  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `h`  
 `CHandle`핸들의 소유권을 갖게 됩니다 `h`합니다.  
  
### <a name="return-value"></a>반환 값  
 새에 대 한 참조를 반환 `CHandle` 개체입니다.  
  
### <a name="remarks"></a>설명  
 경우는 `CHandle` 개체 핸들을 현재 포함, 종료 됩니다. `CHandle` 개체에 전달 되 고 NULL로 설정의 핸들이 참조 해야 합니다. 이렇게 하면 두 `CHandle` 개체 동일한 활성 핸들 포함 됩니다.  
  
##  <a name="operator_handle"></a>CHandle::operator 핸들  
 저장 된 핸들의 값을 반환합니다.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>설명  
 에 저장 된 값을 반환 [CHandle::m_h](#m_h)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
