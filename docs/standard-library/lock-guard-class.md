---
title: "lock_guard 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 047c7ab9db009bceafe47bb0ae53b876adad81b5
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="lockguard-class"></a>lock_guard 클래스
소멸자가 `mutex`의 잠금을 해제하는 개체를 만들기 위해 인스턴스화할 수 있는 템플릿을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Mutex>
class lock_guard;
```  
  
## <a name="remarks"></a>설명  
 템플릿 인수 `Mutex`는 *뮤텍스 형식*의 이름을 지정해야 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`lock_guard::mutex_type`|템플릿 인수 `Mutex`에 대한 동의어입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[lock_guard](#lock_guard)|`lock_guard` 개체를 생성합니다.|  
|[lock_guard::~lock_guard 소멸자](#dtorlock_guard_destructor)|생성자에 전달된 `mutex`를 잠금 해제합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<뮤텍스 >  
  
 **네임스페이스:** std  
  
##  <a name="lock_guard"></a>  lock_guard::lock_guard 생성자  
 `lock_guard` 개체를 생성합니다.  
  
```cpp  
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```  
  
### <a name="parameters"></a>매개 변수  
 `Mtx`  
 *뮤텍스 형식* 개체입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 `lock_guard` 형식의 개체를 생성하고 `Mtx`를 잠급니다. `Mtx`가 재귀 뮤텍스가 아니면 이 생성자를 호출할 때 잠금이 해제되어 있어야 합니다.  
  
 두 번째 생성자는 `Mtx`를 잠그지 않습니다. 이 생성자를 호출할 때 `Mtx`가 잠겨 있어야 합니다. 생성자는 예외를 throw하지 않습니다.  
  
##  <a name="dtorlock_guard_destructor"></a>  lock_guard::~lock_guard 소멸자  
 생성자에 전달된 `mutex`를 잠금 해제합니다.  
  
```
~lock_guard() noexcept;
```  
  
### <a name="remarks"></a>설명  
 소멸자가 실행될 때 `mutex`가 없으면 동작이 정의되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




