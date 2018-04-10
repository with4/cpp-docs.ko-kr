---
title: runtime_exception 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 678f0a93577a6e30afbc5e0c6d83aca6b6a7bedc
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="runtimeexception-class"></a>runtime_exception 클래스
C++ AMP(C++ Accelerated Massive Parallelism) 라이브러리의 예외에 대한 기본 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
class runtime_exception : public std::exception;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[runtime_exception 생성자](#ctor)|`runtime_exception` 클래스의 새 인스턴스를 초기화합니다.|  
|[~ runtime_exception 소멸자](#dtor)|소멸 된 `runtime_exception` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[get_error_code](#runtime_exception__get_error_code)|예외를 발생 시킨 오류 코드가 반환 됩니다.|  

  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator=](#operator_eq)|지정 된의 내용을 복사 `runtime_exception` 을 여기에 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  

## <a name="runtime_exception__ctor"></a>  runtime_exception 생성자  
클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```  
runtime_exception(  
    const char * _Message,  
    HRESULT _Hresult ) throw();  
  
explicit runtime_exception(  
    HRESULT _Hresult ) throw();  
  
runtime_exception(  
    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 예외를 발생 시킨 오류에 대 한 설명  
  
 `_Hresult`  
 예외를 발생 시킨 오류의 HRESULT입니다.  
  
 `_Other`  
 `runtime_exception` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `runtime_exception` 개체  

## <a name="dtor"></a>  ~ runtime_exception 소멸자  
개체를 제거합니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="runtime_exception__get_error_code"></a>  get_error_code   
예외를 발생 시킨 오류 코드가 반환 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>반환 값  
 예외를 발생 시킨 오류의 HRESULT입니다.  
  
## <a name="runtime_exception__operator_eq"></a>  operator=   
  지정 된의 내용을 복사 `runtime_exception` 을 여기에 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
runtime_exception & operator= (    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 `runtime_exception` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `runtime_exception` 개체입니다.  
  

  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
