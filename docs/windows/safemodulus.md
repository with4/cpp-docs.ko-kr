---
title: SafeModulus | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeModulus
dev_langs:
- C++
helpviewer_keywords:
- SafeModulus function
ms.assetid: ae5c81eb-5dcf-45a5-aa76-465fdfe68654
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6eaac98e7794ba9a2475cf7b56641d3a779f84d5
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604887"
---
# <a name="safemodulus"></a>SafeModulus
두 숫자에 대 한 나머지 작업을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T, typename U>  
inline bool SafeModulus (  
   const T t,  
   const U u,  
   T& result  
) throw ();  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *t*  
 제수입니다. 이 형식 이어야 합니다 `T`합니다.  
  
 [in] *u*  
 피제수입니다. 이 형식 이어야 합니다 `U`합니다.  
  
 [out] *결과*  
 매개 변수가 있는 **SafeModulus** 결과 저장 합니다.  
  
## <a name="return-value"></a>반환 값  
 **true** 오류가 발생 하지 않으면; **false** 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 부분 [SafeInt 라이브러리](../windows/safeint-library.md) 의 인스턴스를 만들지 않고 단일 모듈러스 연산에 대 한 설계 되는 [SafeInt 클래스](../windows/safeint-class.md)합니다.  
  
> [!NOTE]
>  이 메서드는 단일 수학 연산을 보호해야 하는 경우에만 사용해야 합니다. 작업이 여러 개 있으면 개별 독립 실행형 함수를 호출하는 대신 `SafeInt` 클래스를 사용해야 합니다.  
  
 템플릿 형식에 대 한 자세한 `T` 하 고 `U`를 참조 하세요 [SafeInt 함수](../windows/safeint-functions.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** microsoft:: utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 함수](../windows/safeint-functions.md)   
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeDivide](../windows/safedivide.md)