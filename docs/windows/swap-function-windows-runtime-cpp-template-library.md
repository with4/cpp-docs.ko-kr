---
title: "Swap 함수 (Windows 런타임 c + + 템플릿 라이브러리) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::Swap
dev_langs: C++
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0b48be8c5cd4702d0d4ee2dd7d541829e3bf94ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="swap-function-windows-runtime-c-template-library"></a>Swap 함수(Windows Runtime C++ 템플릿 라이브러리)
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW inline void Swap(  
   _Inout_ T& left,  
   _Inout_ T& right  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `left`  
 첫 번째 인수입니다.  
  
 `right`  
 두 번째 인수입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 지정된 된 두 인수 값을 교환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)