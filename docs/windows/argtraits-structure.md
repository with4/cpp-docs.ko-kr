---
title: "ArgTraits 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::ArgTraits
dev_langs: C++
helpviewer_keywords: ArgTraits structure
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d95fc547d9c755adad58c1ddcd8de5a8e40a863c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="argtraits-structure"></a>ArgTraits 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename TMemberFunction  
>  
struct ArgTraits;  
template<  
   typename TDelegateInterface  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TMemberFunction`  
 어떤 Invoke 메서드 시그니처를 일치 시킬 수 없는 ArgTraits 구조체에 대 한 매개 변수를 형식 이름입니다.  
  
 `TDelegateInterface`  
 대리자 인터페이스입니다.  
  
 `TArg1`  
 Invoke 메서드의 첫 번째 인수의 형식입니다.  
  
 `TArg2`  
 Invoke 메서드의 두 번째 인수의 형식입니다.  
  
 `TArg3`  
 Invoke 메서드의 세 번째 인수의 형식입니다.  
  
 `TArg4`  
 Invoke 메서드의 네 번째 인수의 형식입니다.  
  
 `TArg5`  
 Invoke 메서드의 다섯 번째 인수의 형식입니다.  
  
 `TArg6`  
 형식 Invoke 메서드의 여섯 번째 인수입니다.  
  
 `TArg7`  
 형식 Invoke 메서드의 일곱 번째 인수입니다.  
  
 `TArg8`  
 형식 Invoke 메서드의 여덟 번째 인수입니다.  
  
 `TArg9`  
 아홉 번째 인수는 호출 메서드의 형식입니다.  
  
## <a name="remarks"></a>설명  
 `ArgTraits` 구조 인터페이스 및 지정된 된 수의 매개 변수를 가진 익명 멤버 함수는 지정 된 대리자를 선언 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Arg1Type`|TArg1에 대 한 typedef입니다.|  
|`Arg2Type`|TArg2에 대 한 typedef입니다.|  
|`Arg3Type`|TArg3에 대 한 typedef입니다.|  
|`Arg4Type`|TArg4에 대 한 typedef입니다.|  
|`Arg5Type`|TArg5에 대 한 typedef입니다.|  
|`Arg6Type`|TArg6에 대 한 typedef입니다.|  
|`Arg7Type`|TArg7에 대 한 typedef입니다.|  
|`Arg8Type`|TArg8에 대 한 typedef입니다.|  
|`Arg9Type`|TArg9에 대 한 typedef입니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[ArgTraits::args 상수](../windows/argtraits-args-constant.md)|Invoke 메서드를 대리자 인터페이스에 대 한 매개 변수 개수의 수를 유지 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ArgTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)