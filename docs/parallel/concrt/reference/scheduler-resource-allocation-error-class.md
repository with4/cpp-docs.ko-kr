---
title: "scheduler_resource_allocation_error 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::scheduler_resource_allocation_error
dev_langs:
- C++
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 52233a99e1d1a715fc7d52599ffeff18a3c2c34b
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error 클래스
이 클래스는 동시성 런타임에서 중요한 리소스를 얻지 못해 발생하는 예외를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
class scheduler_resource_allocation_error : public std::exception;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[scheduler_resource_allocation_error 생성자](#ctor)|오버로드됨. `scheduler_resource_allocation_error` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[get_error_code 메서드](#get_error_code)|예외를 발생 시킨 오류 코드를 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 이 예외는 일반적으로 동시성 런타임 내에서 운영 체제 호출이 실패할 때 throw 됩니다. 일반적으로 Win32 메서드 `GetLastError`에 대한 호출에서 반환되는 오류 코드는 `HRESULT` 형식의 값으로 변환되므로 `get_error_code` 메서드를 사용하여 검색할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namegeterrorcodea-geterrorcode"></a><a name="get_error_code"></a>get_error_code 

 예외를 발생 시킨 오류 코드를 반환 합니다.  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 `HRESULT` 예외를 발생 시킨 오류 값입니다.  
  
##  <a name="a-namectora-schedulerresourceallocationerror"></a><a name="ctor"></a>scheduler_resource_allocation_error 

 `scheduler_resource_allocation_error` 개체를 생성합니다.  
  
```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  
 `_Hresult`  
 `HRESULT` 예외를 발생 시킨 오류 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)

