---
title: "runtime_exception 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 399d2531c06285012df12d703b4cda6e18469c38
ms.lasthandoff: 03/17/2017

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
|[~ runtime_exception 소멸자](#dtor)|소멸은 `runtime_exception` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[get_error_code](#runtime_exception__get_error_code)|예외를 발생 시킨 오류 코드를 반환 합니다.|  

  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator=](#operator_eq)|지정 된 내용을 복사 `runtime_exception` 을 여기에 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  

## <a name="runtime_exception__ctor"></a>runtime_exception 생성자  
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
 예외를 발생 시킨 오류에 대 한 설명입니다.  
  
 `_Hresult`  
 예외를 발생 시킨 오류의 HRESULT입니다.  
  
 `_Other`  
 `runtime_exception` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `runtime_exception` 개체  

## <a name="dtor"></a>~ runtime_exception 소멸자  
개체를 소멸 시킵니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="runtime_exception__get_error_code"></a>get_error_code   
예외를 발생 시킨 오류 코드를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>반환 값  
 예외를 발생 시킨 오류의 HRESULT입니다.  
  
## <a name="runtime_exception__operator_eq"></a>  operator=   
  지정 된 내용을 복사 `runtime_exception` 을 여기에 개체입니다.  
  
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

