---
title: "Make 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Make
dev_langs: C++
helpviewer_keywords: Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aac2a50e3c50941d607dea32c9f7c9eecde8e589
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="make-function"></a>Make 함수
지정된 된 Windows 런타임 클래스를 초기화합니다. 이 함수는 동일한 모듈에 정의 된 구성 요소의 인스턴스를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 상속 되는 사용자 지정 클래스 `WRL::RuntimeClass`합니다.  
  
 `TArg1`  
 지정된 된 런타임 클래스에 전달 되는 1 인수 형식입니다.  
  
 `TArg2`  
 지정된 된 런타임 클래스에 전달 되는 인수 2 형식입니다.  
  
 `TArg3`  
 지정된 된 런타임 클래스에 전달 되는 3 인수 형식입니다.  
  
 `TArg4`  
 지정된 된 런타임 클래스에 전달 되는 4 인수 형식입니다.  
  
 `TArg5`  
 지정된 된 런타임 클래스에 전달 되는 5 인수 형식입니다.  
  
 `TArg6`  
 지정된 된 런타임 클래스에 전달 되는 인수 6 형식입니다.  
  
 `TArg7`  
 지정된 된 런타임 클래스에 전달 되는 7 인수 형식입니다.  
  
 `TArg8`  
 지정된 된 런타임 클래스에 전달 되는 8 인수 형식입니다.  
  
 `TArg9`  
 지정된 된 런타임 클래스에 전달 되는 9 인수 형식입니다.  
  
 `arg1`  
 인수 1 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 `arg2`  
 인수 2 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 `arg3`  
 인수 3 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 `arg4`  
 인수 4 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 `arg5`  
 인수 5 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 `arg6`  
 인수 6 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 `arg7`  
 인수 7 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 `arg8`  
 인수 8 지정된 된 런타임 클래스에 전달 되는입니다.  
  
 `arg9`  
 인수 9 지정된 된 런타임 클래스에 전달 되는입니다.  
  
## <a name="return-value"></a>반환 값  
 A `ComPtr<T>` 개체 고, 그렇지 않으면 성공 `nullptr`합니다.  
  
## <a name="remarks"></a>설명  
 참조 [하는 방법: 직접 WRL 구성 요소를 인스턴스화할](../windows/how-to-instantiate-wrl-components-directly.md) 이 함수 간의 차이점을 파악 하 고 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md), 및 예제입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)