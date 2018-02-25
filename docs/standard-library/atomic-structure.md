---
title: "atomic 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e5e7de7a5098aec10618c961444eb73b4597d0fc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="atomic-structure"></a>atomic 구조체
`Ty` 형식의 저장된 값에 대해 원자 연산을 수행하는 개체를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Ty>
struct atomic;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[atomic](http://msdn.microsoft.com/Library/a538c43f-4d48-4308-ae1b-bab1839bccb8)|atomic 개체를 생성합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[atomic::operator Ty 연산자](http://msdn.microsoft.com/Library/a366c700-c7a0-4bcb-8eb4-4b57dfaea065)|저장된 값을 읽고 반환합니다. ([atomic::load](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1))|  
|[atomic::operator= 연산자](http://msdn.microsoft.com/Library/fe161d57-47ae-4bad-92bf-ce32ac8d5953)|지정된 값을 사용하여 저장된 값을 바꿉니다. ([atomic::store](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b))|  
|[atomic::operator++ 연산자](http://msdn.microsoft.com/Library/492959e9-1ea8-4e02-a031-82b1b92e91a0)|저장된 값을 증가시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|  
|[atomic::operator+= 연산자](http://msdn.microsoft.com/Library/9ec97aa2-c9d7-436b-943d-2989eb2617dd)|지정된 값을 저장된 값에 더합니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|  
|[atomic::operator-- 연산자](http://msdn.microsoft.com/Library/ad7c1ea7-1f6d-4a54-bf26-07630f749864)|저장된 값을 감소시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|  
|[atomic::operator-= 연산자](http://msdn.microsoft.com/Library/902d0d9f-88fd-4500-aa2d-1e50f443e77c)|지정된 값을 저장된 값에서 뺍니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|  
|[atomic::operator&= 연산자](http://msdn.microsoft.com/Library/90e730ac-12e1-4abb-98f5-4eadd6861a89)|지정된 값 및 저장된 값에서 비트 `and`를 수행합니다. 정수 계열 특수화에서만 사용됩니다.|  
|[atomic::operator&#124;= 연산자](http://msdn.microsoft.com/Library/f105eacc-31a6-4906-abba-f1cf013599b2)|지정된 값 및 저장된 값에서 비트 `or`를 수행합니다. 정수 계열 특수화에서만 사용됩니다.|  
|[atomic::operator^= 연산자](http://msdn.microsoft.com/Library/f2a4da9d-67e8-4249-9161-9998e72a33c2)|지정된 값 및 저장된 값에서 비트 `exclusive or`를 수행합니다. 정수 계열 특수화에서만 사용됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[compare_exchange_strong](http://msdn.microsoft.com/Library/47bbf894-b28c-4ece-959e-67b3863cf4ed)|`this`에서 `atomic_compare_and_exchange` 연산을 수행하고 결과를 반환합니다.|  
|[compare_exchange_weak](http://msdn.microsoft.com/Library/e15e421a-f7a3-4272-993a-f487d2242e4f)|`this`에서 `weak_atomic_compare_and_exchange` 연산을 수행하고 결과를 반환합니다.|  
|[fetch_add](http://msdn.microsoft.com/Library/c68b91f2-6e8a-4ffa-8991-6bb6d466e1f3)|지정된 값을 저장된 값에 더합니다.|  
|[fetch_and](http://msdn.microsoft.com/Library/a9c83001-b72c-4085-9640-f63f866714b9)|지정된 값 및 저장된 값에서 비트 `and`를 수행합니다.|  
|[fetch_or](http://msdn.microsoft.com/Library/4c532f7f-80c5-432a-b34b-48feacab8dca)|지정된 값 및 저장된 값에서 비트 `or`를 수행합니다.|  
|[fetch_sub](http://msdn.microsoft.com/Library/8cc80d4b-0942-45a3-9db8-bbf339a903e4)|지정된 값을 저장된 값에서 뺍니다.|  
|[fetch_xor](http://msdn.microsoft.com/Library/92bbaff8-ee29-4a1e-aee4-d9d405285bfe)|지정된 값 및 저장된 값에서 비트 `exclusive or`를 수행합니다.|  
|[is_lock_free](http://msdn.microsoft.com/Library/b99d5130-cdda-40a2-b14c-152b13a8ba45)|`this`의 원자 연산이 *잠금 해제*인지를 지정합니다. 원자 형식의 어떤 원자 연산도 잠금을 사용하지 않는 경우 해당 원자 형식을 *잠금 해제*라고 합니다.|  
|[load](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1)|저장된 값을 읽고 반환합니다.|  
|[store](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b)|지정된 값을 사용하여 저장된 값을 바꿉니다.|  
  
## <a name="remarks"></a>설명  
 `Ty` 형식은 *일반적으로 복사 가능*해야 합니다. [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)를 사용하여 바이트를 복사하면 비교 시 원본 개체와 같은 유효한 `Ty` 개체가 생성되어야 합니다. `compare_exchange_weak` 및 `compare_exchange_strong` 멤버 함수는 [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)를 사용하여 두 개의 `Ty` 값이 같은지 확인합니다. 이러한 함수는 `operator==`에 정의된 `Ty`를 사용하지 않습니다. `atomic`의 멤버 함수는 `memcpy`를 사용하여 `Ty` 형식의 값을 복사합니다.  
  
 부분 특수화 `atomic<Ty *>`는 모든 포인터 형식에 대해 존재합니다. 특수화를 사용하면 관리되는 포인터 값에 오프셋을 더하거나 값에서 오프셋을 뺄 수 있습니다. 산술 연산은 `ptrdiff_t` 형식의 인수를 가져와서 `Ty`의 크기에 따라 일반 주소 산술과 일관되게 조정합니다.  
  
 특수화는 `bool`을 제외한 모든 정수 형식에 대해 존재합니다. 각 특수화에서는 원자 산술 및 논리 연산을 위한 다양한 방법을 제공합니다.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 정수 특수화는 해당 `atomic_integral` 형식에서 파생됩니다. 예를 들어 `atomic<unsigned int>`는 `atomic_uint`에서 파생됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<원자성 >  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [\<atomic>](../standard-library/atomic.md)   
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)



