---
title: "CHandle 클래스 | Microsoft 문서"
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
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: bbc0703ae5eaab01c0819be7e378509c7dc579ef
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="chandle-class"></a>CHandle 클래스
이 클래스를 만들고 핸들 개체를 사용 하는 메서드를 제공 합니다.  
  
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
|[CHandle::Close](#close)|닫으려면이 메서드를 호출 하는 `CHandle` 개체입니다.|  
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
  
## <a name="remarks"></a>주의  
 A `CHandle` 개체 핸들을이 필요할 때마다 사용할 수 있습니다: 주요 차이점은는 `CHandle` 개체는 자동으로 삭제 됩니다.  
  
> [!NOTE]
>  INVALID_HANDLE_VALUE 사용 하 고 다른 일부 API 함수는 비어 있거나 잘못 된 핸들로 NULL을 사용 합니다. `CHandle`실제 핸들으로 INVALID_HANDLE_VALUE를 처리 하는 NULL 및을 사용 합니다. 호출 하기 전에이 값을 확인 해야 INVALID_HANDLE_VALUE를 반환할 수 있는 API를 호출 하면 [CHandle::Attach](#attach) 또는 전달 하는 `CHandle` 생성자를 대신 NULL을 전달 합니다.  
  
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
  
### <a name="remarks"></a>주의  
 할당은 `CHandle` 개체는 `h` 처리 합니다. 디버그 빌드에서 ATLASSERT 발생 합니다 `h` 은 NULL입니다. 다른 검사가 핸들의 유효성이 수행 되지 않습니다.  
  
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
  
### <a name="remarks"></a>주의  
 새로 만듭니다 `CHandle` 필요에 따라 기존 핸들을 사용 하 여 개체 또는 `CHandle` 개체입니다.  
  
##  <a name="dtor"></a>CHandle:: ~ CHandle  
 소멸자입니다.  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>주의  
 해제는 `CHandle` 개체를 호출 하 여 [CHandle::Close](#close)합니다.  
  
##  <a name="close"></a>CHandle::Close  
 닫으려면이 메서드를 호출 하는 `CHandle` 개체입니다.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>주의  
 열려 있는 개체 핸들을 닫습니다. 핸들이 NULL 인 경우 될 경우 **닫기** 가 이미 호출 된 ATLASSERT 발생 합니다 디버그 빌드에 있습니다.  
  
##  <a name="detach"></a>CHandle::Detach  
 핸들을 분리 하려면이 메서드를 호출 하는 `CHandle` 개체입니다.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 분리 되는 핸들을 반환 합니다.  
  
### <a name="remarks"></a>주의  
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
 새에 대 한 참조를 반환 합니다. `CHandle` 개체입니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `CHandle` 개체에 대 한 핸들을 현재 포함, 닫힙니다. `CHandle` 개체에 전달 되는 핸들 대 한 참조를 NULL로 설정 합니다. 이렇게 하면 두 개의 `CHandle` 같은 활성 핸들이 포함 되지 않는 개체입니다.  
  
##  <a name="operator_handle"></a>CHandle::operator 핸들  
 저장 된 핸들의 값을 반환합니다.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>주의  
 에 저장 된 값을 반환 [CHandle::m_h](#m_h)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

