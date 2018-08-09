---
title: Make 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
dev_langs:
- C++
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0076445f21bcbad5ca7028c088cddfdbdcacf8cd
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013703"
---
# <a name="make-function"></a>Make 함수
지정된 된 Windows 런타임 클래스를 초기화합니다. 이 함수를 사용 하 여 동일한 모듈에 정의 된 구성 요소를 인스턴스화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
   typename T,  
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
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8,  
   TArg9 &&arg9  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2  
);  
template <  
   typename T,  
   typename TArg1  
>  
ComPtr<T> Make(  
   TArg1 &&arg1  
);  
template <  
   typename T  
>  
ComPtr<T> Make();  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 사용자 지정 클래스에서 상속 되는 `WRL::RuntimeClass`합니다.  
  
 *TArg1*  
 지정된 된 런타임 클래스에 전달 되는 인수 1의 형식입니다.  
  
 *TArg2*  
 지정된 된 런타임 클래스에 전달 되는 2 인수 형식입니다.  
  
 *TArg3*  
 지정된 된 런타임 클래스에 전달 되는 3 번째 인수의 형식입니다.  
  
 *TArg4*  
 지정된 된 런타임 클래스에 전달 되는 4 번째 인수의 형식입니다.  
  
 *TArg5*  
 지정된 된 런타임 클래스에 전달 되는 5 번째 인수의 형식입니다.  
  
 *TArg6*  
 지정된 된 런타임 클래스에 전달 되는 6 번째 인수의 형식입니다.  
  
 *TArg7*  
 지정된 된 런타임 클래스에 전달 되는 7 번째 인수의 형식입니다.  
  
 *TArg8*  
 지정된 된 런타임 클래스에 전달 되는 8 번째 인수의 형식입니다.  
  
 *TArg9*  
 지정된 된 런타임 클래스에 전달 되는 9 번째 인수의 형식입니다.  
  
 *arg1*  
 인수 1 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 *Arg2*  
 인수 2 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 *arg3*  
 인수 3 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 *arg4*  
 인수 4 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 *arg5*  
 인수 5 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 *a r g 6*  
 인수 6 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 *arg7*  
 7 전달 된 인수를 지정 된 런타임 클래스입니다.  
  
 *arg8*  
 8 전달 된 인수를 지정 된 런타임 클래스입니다.  
  
 *arg9*  
 9 전달 된 인수를 지정 된 런타임 클래스입니다.  
  
## <a name="return-value"></a>반환 값  
 A `ComPtr<T>` 개체가 고, 그렇지 않으면 성공적인 **nullptr**합니다.  
  
## <a name="remarks"></a>설명  
 참조 [방법: 직접 WRL 구성 요소 인스턴스화](../windows/how-to-instantiate-wrl-components-directly.md) 이 함수 간의 차이점을 알아보려면 및 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md), 및 예제입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)