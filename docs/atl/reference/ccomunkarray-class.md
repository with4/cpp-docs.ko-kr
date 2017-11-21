---
title: "CComUnkArray 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
dev_langs: C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 14c2b7e05ed303d8b18ae40619bc63a75f025662
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomunkarray-class"></a>CComUnkArray 클래스
이 클래스는 저장 **IUnknown** 포인터에 대 한 매개 변수로 사용할 수 있도록 설계 되 고는 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>매개 변수  
 *nMaxSize*  
 최대 **IUnknown** 정적 배열에 저장할 수 있는 포인터입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](#ccomunkarray)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComUnkArray::Add](#add)|이 메서드를 호출 추가 **IUnknown** 배열에 대 한 포인터입니다.|  
|[CComUnkArray::begin](#begin)|첫 번째에 대 한 포인터를 반환 **IUnknown** 컬렉션에 대 한 포인터입니다.|  
|[CComUnkArray::end](#end)|마지막 지난 다음 요소에 대 한 포인터를 반환 **IUnknown** 컬렉션에 대 한 포인터입니다.|  
|[CComUnkArray::GetCookie](#getcookie)|와 연관 된 쿠키를 가져오려면이 메서드를 호출 하는 지정 된 **IUnknown** 포인터입니다.|  
|[CComUnkArray::GetUnknown](#getunknown)|가져오려면이 메서드를 호출 하는 **IUnknown** 지정된 쿠키와 관련 된 포인터입니다.|  
|[CComUnkArray::Remove](#remove)|제거 하려면이 메서드를 호출 하는 **IUnknown** 배열에서 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 **CComUnkArray** 고정된 된 수의 보유 **IUnknown** 포인터, 각 인터페이스에 대 한 연결 지점입니다. **CComUnkArray** 매개 변수로 사용할 수는 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스입니다. **CComUnkArray\<1 >** 의 템플릿 특수화 **CComUnkArray** 하나의 연결 지점에 대해 최적화 되었습니다.  
  
 **CComUnkArray** 메서드 [시작](#begin) 및 [끝](#end) 는 모든 연결 지점 (예: 이벤트가 발생 하는 경우)를 반복 하는 데 사용할 수 있습니다.  
  
 참조 [개체에 추가 연결 지점을](../../atl/adding-connection-points-to-an-object.md) 연결 만들기를 자동화에 대 한 내용은 프록시를 가리킵니다.  
  
> [!NOTE]
> **참고** 클래스 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) 에서 사용 되는 **클래스 추가** 연결점에 컨트롤을 만들 때 마법사. 연결 지점의 수를 수동으로 지정 하려는 경우 해당 참조 변경 **CComDynamicUnkArray** 를 `CComUnkArray<`  *n*  `>`여기서  *n*  필요한 연결 지점의 수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="add"></a>CComUnkArray::Add  
 이 메서드를 호출 추가 **IUnknown** 배열에 대 한 포인터입니다.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 이 메서드를 호출 추가 **IUnknown** 배열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 배열의 새 포인터를 포함할 수 없는 경우 새로 추가 된 포인터 또는 0와 연관 된 쿠키를 반환 합니다.  
  
##  <a name="begin"></a>CComUnkArray::begin  
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
  
##  <a name="ccomunkarray"></a>CComUnkArray::CComUnkArray  
 생성자입니다.  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>설명  
 보관할 컬렉션 설정 `nMaxSize` **IUnknown** 포인터에 대 한 포인터를 초기화 하 고 **NULL**합니다.  
  
##  <a name="end"></a>CComUnkArray::end  
 마지막 지난 다음 요소에 대 한 포인터를 반환 **IUnknown** 컬렉션에 대 한 포인터입니다.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 **IUnknown** 인터페이스 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `CComUnkArray` 메서드 **시작** 및 **끝** 이벤트가 발생할 때 모든 연결 지점을 통해 예를 들어, 루프 데 사용할 수 있습니다.  
  
 [!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="getcookie"></a>CComUnkArray::GetCookie  
 와 연관 된 쿠키를 가져오려면이 메서드를 호출 하는 지정 된 **IUnknown** 포인터입니다.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppFind`  
 **IUnknown** 포인터가 관련된 쿠키가 필요 합니다.  
  
### <a name="return-value"></a>반환 값  
 와 연관 된 쿠키를 반환 합니다.는 **IUnknown** 포인터 또는 일치 하는 경우에 0 **IUnknown** 포인터를 찾을 수 있습니다.  
  
### <a name="remarks"></a>설명  
 동일한 인스턴스가 여러 개 있는지 **IUnknown** 포인터인 경우이 함수에 대 한 첫 번째 쿠키를 반환 합니다.  
  
##  <a name="getunknown"></a>CComUnkArray::GetUnknown  
 가져오려면이 메서드를 호출 하는 **IUnknown** 지정된 쿠키와 관련 된 포인터입니다.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCookie`  
 쿠키를 연결 된 **IUnknown** 포인터가 필요 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 **IUnknown** 포인터 또는 일치 하는 쿠키가 없는 경우 NULL입니다.  
  
##  <a name="remove"></a>CComUnkArray::Remove  
 제거 하려면이 메서드를 호출 하는 **IUnknown** 배열에서 포인터입니다.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCookie`  
 참조 하는 쿠키는 **IUnknown** 배열에서 제거할 수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 포인터 제거 되 면 **FALSE** 그렇지 않은 경우.  
  
## <a name="see-also"></a>참고 항목  
 [CComDynamicUnkArray 클래스](../../atl/reference/ccomdynamicunkarray-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
