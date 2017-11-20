---
title: "CComDynamicUnkArray 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs: C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 51ad16bacf147e2bafc1cc2ad1a9bb835067ee40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray 클래스
이 클래스의 배열을 저장 **IUnknown** 포인터입니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComDynamicUnkArray
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|생성자입니다. 컬렉션 값을 초기화 **NULL** 및 컬렉션 크기를 0으로 합니다.|  
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](#add)|이 메서드를 호출 추가 `IUnknown` 배열에 대 한 포인터입니다.|  
|[CComDynamicUnkArray::begin](#begin)|첫 번째에 대 한 포인터를 반환 `IUnknown` 컬렉션에 대 한 포인터입니다.|  
|[CComDynamicUnkArray::clear](#clear)|배열을 비웁니다.|  
|[CComDynamicUnkArray::end](#end)|마지막 지난 다음 요소에 대 한 포인터를 반환 **IUnknown** 컬렉션에 대 한 포인터입니다.|  
|[CComDynamicUnkArray::GetAt](#getat)|지정된 된 인덱스에 요소를 검색 합니다.|  
|[CComDynamicUnkArray::GetCookie](#getcookie)|와 연관 된 쿠키를 가져오려면이 메서드를 호출 하는 지정 된 **IUnknown** 포인터입니다.|  
|[CComDynamicUnkArray::GetSize](#getsize)|배열 길이 반환합니다.|  
|[CComDynamicUnkArray::GetUnknown](#getunknown)|가져오려면이 메서드를 호출 하는 **IUnknown** 지정된 쿠키와 관련 된 포인터입니다.|  
|[CComDynamicUnkArray::Remove](#remove)|제거 하려면이 메서드를 호출 하는 **IUnknown** 배열에서 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 **CComDynamicUnkArray** 동적으로 할당 된 배열을 보유 **IUnknown** 포인터, 각 인터페이스에 대 한 연결 지점입니다. **CComDynamicUnkArray** 매개 변수로 사용할 수는 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스입니다.  
  
 **CComDynamicUnkArray** 메서드 [시작](#begin) 및 [끝](#end) 는 모든 연결 지점 (예: 이벤트가 발생 하는 경우)를 반복 하는 데 사용할 수 있습니다.  
  
 참조 [개체에 추가 연결 지점을](../../atl/adding-connection-points-to-an-object.md) 연결 만들기를 자동화에 대 한 내용은 프록시를 가리킵니다.  
  
> [!NOTE]
> **참고** 클래스 **CComDynamicUnkArray** 에서 사용 되는 **클래스 추가** 연결점에 컨트롤을 만들 때 마법사. 연결 지점의 수를 수동으로 지정 하려는 경우 해당 참조 변경 **CComDynamicUnkArray** 를 `CComUnkArray<`  *n*  `>`여기서  *n*  필요한 연결 지점의 수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="add"></a>CComDynamicUnkArray::Add  
 이 메서드를 호출 추가 **IUnknown** 배열에 대 한 포인터입니다.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 **IUnknown** 배열에 추가할에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 추가 된 포인터와 연관 된 쿠키를 반환 합니다.  
  
##  <a name="begin"></a>CComDynamicUnkArray::begin  
 컬렉션의 시작 부분에 대 한 포인터를 반환 **IUnknown** 인터페이스 포인터입니다.  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 **IUnknown** 인터페이스 포인터입니다.  
  
### <a name="remarks"></a>설명  
 컬렉션에 로컬로 저장 하는 인터페이스에 대 한 포인터 **IUnknown**합니다. 각 캐스팅 **IUnknown** 실제 인터페이스 형식으로 인터페이스를 통해 호출 합니다. 인터페이스에 대해 먼저 쿼리할 필요가 없습니다.  
  
 사용 하기 전에 **IUnknown** 인터페이스를 확인 해야 아닌지 **NULL**합니다.  
  
##  <a name="clear"></a>CComDynamicUnkArray::clear  
 배열을 비웁니다.  
  
```
void clear();
```  
  
##  <a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray  
 생성자입니다.  
  
```
CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>설명  
 컬렉션 크기를 0으로 설정 하 고 값을 초기화 **NULL**합니다. 필요한 경우 소멸자는 컬렉션을 해제 합니다.  
  
##  <a name="dtor"></a>CComDynamicUnkArray:: ~ CComDynamicUnkArray  
 소멸자입니다.  
  
```
~CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>설명  
 클래스 생성자에 의해 할당 된 리소스를 해제 합니다.  
  
##  <a name="end"></a>CComDynamicUnkArray::end  
 마지막 지난 다음 요소에 대 한 포인터를 반환 **IUnknown** 컬렉션에 대 한 포인터입니다.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 **IUnknown** 인터페이스 포인터입니다.  
  
##  <a name="getat"></a>CComDynamicUnkArray::GetAt  
 지정된 된 인덱스에 요소를 검색 합니다.  
  
```
IUnknown* GetAt(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 검색할 요소의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 인터페이스입니다.  
  
##  <a name="getcookie"></a>CComDynamicUnkArray::GetCookie  
 와 연관 된 쿠키를 가져오려면이 메서드를 호출 하는 지정 된 **IUnknown** 포인터입니다.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppFind`  
 **IUnknown** 포인터가 관련된 쿠키가 필요 합니다.  
  
### <a name="return-value"></a>반환 값  
 와 연관 된 쿠키를 반환 합니다.는 **IUnknown** 포인터 또는 일치 하는 경우 0 **IUnknown** 포인터를 찾을 수 있습니다.  
  
### <a name="remarks"></a>설명  
 동일한 인스턴스가 여러 개 있는지 **IUnknown** 포인터인 경우이 함수에 대 한 첫 번째 쿠키를 반환 합니다.  
  
##  <a name="getsize"></a>CComDynamicUnkArray::GetSize  
 배열 길이 반환합니다.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>반환 값  
 배열의 길이입니다.  
  
##  <a name="getunknown"></a>CComDynamicUnkArray::GetUnknown  
 가져오려면이 메서드를 호출 하는 **IUnknown** 지정된 쿠키와 관련 된 포인터입니다.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCookie`  
 쿠키를 연결 된 **IUnknown** 포인터가 필요 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 **IUnknown** 포인터 또는 일치 하는 쿠키가 없는 경우 NULL입니다.  
  
##  <a name="remove"></a>CComDynamicUnkArray::Remove  
 제거 하려면이 메서드를 호출 하는 **IUnknown** 배열에서 포인터입니다.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCookie`  
 참조 하는 쿠키는 **IUnknown** 배열에서 제거할 수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 포인터 제거 되는 경우 TRUE를 반환합니다 그렇지 않으면 FALSE입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComUnkArray 클래스](../../atl/reference/ccomunkarray-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
