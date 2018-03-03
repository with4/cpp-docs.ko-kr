---
title: "Mutex:: operator = 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23526911a2d9e723455a7d846bdaafb2dbefd45a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mutexoperator-operator"></a>Mutex::operator= 연산자
현재 Mutex 개체를 할당 합니다 (이동) 지정 된 뮤텍스 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `h`  
 뮤텍스 개체 rvalue 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 현재 Mutex 개체에 대 한 참조입니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조는 **이동 의미 체계** 섹션 [Rvalue 참조 선언 자: & &](../cpp/rvalue-reference-declarator-amp-amp.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>참고 항목
 [Mutex 클래스](../windows/mutex-class1.md)