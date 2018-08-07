---
title: MakeAndInitialize 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAndInitialize
dev_langs:
- C++
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cbdb6a312d6658fc880aa43ffc1205378d3935e7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607652"
---
# <a name="makeandinitialize-function"></a>MakeAndInitialize 함수
지정된 된 Windows 런타임 클래스를 초기화합니다. 이 함수를 사용 하 여 동일한 모듈에 정의 된 구성 요소를 인스턴스화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <typename T, typename I,   
typename TArg1,   
typename TArg2,   
typename TArg3,   
typename TArg4,   
typename TArg5,   
typename TArg6,   
typename TArg7,   
typename TArg8,   
typename TArg9> HRESULT MakeAndInitialize(_Outptr_result_nullonfailure_ I** ppvObject, TArg1 &&arg1, TArg2 &&arg2, TArg3 &&arg3, TArg4 &&arg4, TArg5 &&arg5, TArg6 &&arg6, TArg7 &&arg7, TArg8 &&arg8, TArg9 &&arg9) throw()  
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
 HRESULT 값입니다.  
  
## <a name="remarks"></a>설명  
 참조 [방법: 직접 WRL 구성 요소 인스턴스화](../windows/how-to-instantiate-wrl-components-directly.md) 이 함수 간의 차이점을 알아보려면 및 [Microsoft::WRL::Make](../windows/make-function.md), 및 예제입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)