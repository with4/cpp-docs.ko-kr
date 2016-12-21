---
title: "ArgTraits 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::ArgTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraits 구조체"
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ArgTraits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `TMemberFunction`  
 일치 될 수 없는 ArgTratis 구조체에 대한 형식이름 매개변수는 메서드 서명을 호출합니다.  
  
 `TDelegateInterface`  
 대리자 인터페이스입니다.  
  
 `TArg1`  
 호출 메서드의 첫 번째 인수의 형식  
  
 `TArg2`  
 호출 메서드의 두 번째 인수의 형식  
  
 `TArg3`  
 호출 메서드의 세 번째 인수의 형식  
  
 `TArg4`  
 호출 메서드의 네 번째 인수의 형식  
  
 `TArg5`  
 호출 메서드의 다섯 번째 인수의 형식  
  
 `TArg6`  
 호출 메서드의 여섯 번째 인수의 형식  
  
 `TArg7`  
 호출 메서드의 일곱 번째 인수의 형식  
  
 `TArg8`  
 호출 메서드의 여덟 번째 인수의 형식  
  
 `TArg9`  
 호출 메서드의 아홉 번째 인수의 형식  
  
## 설명  
 `ArgTraits` 구조체 인터페이스 및 익명 멤버 함수는 지정된 개수의 매개 변수로 지정된 대리자를 선언 합니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`Arg1Type`|TArg1는 형식 정의입니다.|  
|`Arg2Type`|TArg2는 형식 정의입니다.|  
|`Arg3Type`|TArg3는 형식 정의입니다.|  
|`Arg4Type`|TArg4는 형식 정의입니다.|  
|`Arg5Type`|TArg5는 형식 정의입니다.|  
|`Arg6Type`|TArg6는 형식 정의입니다.|  
|`Arg7Type`|TArg7는 형식 정의입니다.|  
|`Arg8Type`|TArg8는 형식 정의입니다.|  
|`Arg9Type`|TArg9는 형식 정의입니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[ArgTraits::args 상수](../windows/argtraits-args-constant.md)|호출 메서드는 대리자 인터페이스에 매개 변수의 수를 유지합니다.|  
  
## 상속 계층  
 `ArgTraits`  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)