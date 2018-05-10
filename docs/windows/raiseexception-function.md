---
title: RaiseException 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
dev_langs:
- C++
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2af97ac13386db450318f4d1f384517a8dd77baf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="raiseexception-function"></a>RaiseException 함수
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline void __declspec(noreturn)   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hr`  
 발생 중인; 예외의 예외 코드 즉, 작업 실패의 HRESULT입니다.  
  
 `dwExceptionFlags`  
 비연속적 예외가 (플래그 값은 0), 또는 (플래그 값은 0이 아닌) noncontinuable 예외를 나타내는 플래그입니다. 기본적으로는 예외는 계속할 수 없는입니다.  
  
## <a name="remarks"></a>설명  
 호출 스레드에서 예외가 발생합니다.  
  
 자세한 내용은 참조는 Windows **RaiseException** 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)