---
title: 'Mutex:: operator = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 837c8ed508b713f790d1a6a56310705a00f12b3f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602748"
---
# <a name="mutexoperator-operator"></a>Mutex::operator= 연산자
할당 된 (이동) **뮤텍스** 개체를 현재 **뮤텍스** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *h*  
 rvalue 참조를 **뮤텍스** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 현재에 대 한 참조가 **뮤텍스** 개체입니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조는 **이동 의미 체계** 부분 [Rvalue 참조 선언 자: & &](../cpp/rvalue-reference-declarator-amp-amp.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>참고 항목
 [Mutex 클래스](../windows/mutex-class1.md)