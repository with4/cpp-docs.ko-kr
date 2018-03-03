---
title: "CComPtr 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
dev_langs:
- C++
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ef8c49b04a769fd6202aa58324f20216948cf3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomptr-class"></a>CComPtr 클래스
COM 인터페이스 포인터를 관리 하기 위한 스마트 포인터 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class CComPtr
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 저장할 수에 대 한 포인터의 유형을 지정 하는 COM 인터페이스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComPtr::CComPtr](#ccomptr)|생성자입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CComPtr::operator =](#operator_eq)|멤버 포인터에 대 한 포인터를 할당합니다.|  
  
## <a name="remarks"></a>설명  
 ATL 사용 하 여 `CComPtr` 및 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM 인터페이스 포인터를 관리할 수 있습니다. 둘 다에서 파생 된 [CComPtrBase](../../atl/reference/ccomptrbase-class.md), 둘 다 자동 참조 계산을 수행 합니다.  
  
 **CComPtr** 및 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 클래스 자동 참조 계산을 수행 하 여 메모리 누수를 제거할 수 있습니다.  다음 함수 모두 동일한 논리 연산을; 수행 그러나 어떻게 두 번째 버전 수 오류가 발생할 가능성이 감소를 사용 하 여 메모는 **CComPtr** 클래스:  
  
 [!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]  
  
 디버그 빌드에 코드 추적에 대 한 atlsd.lib를 연결 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="ccomptr"></a>CComPtr::CComPtr  
 생성자입니다.  
  
```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```  
  
### <a name="parameters"></a>매개 변수  
 `lp`  
 인터페이스 포인터를 초기화 하는 데 사용 합니다.  
  
 `T`  
 COM 인터페이스입니다.  
  
##  <a name="operator_eq"></a>CComPtr::operator =  
 대입 연산자입니다.  
  
```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```  
  
### <a name="return-value"></a>반환 값  
 업데이트 된에 대 한 포인터를 반환 `CComPtr` 개체  
  
### <a name="remarks"></a>설명  
 이 작업 AddRefs 새 개체 및 릴리스 경우 기존 개체가 존재 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComPtr::CComPtr](#ccomptr)   
 [CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)   
 [클래스 개요](../../atl/atl-class-overview.md)
