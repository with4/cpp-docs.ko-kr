---
title: "conditional 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::conditional
dev_langs: C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a106f2361dccbeb33c662c88edd40223a604639
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="conditional-class"></a>conditional 클래스
지정된 조건에 따라 두 가지 형식 중 하나를 선택합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <bool B, class T1, class T2>  
struct conditional;

template <bool _Test, class _T1, class _T2>  
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```  
  
#### <a name="parameters"></a>매개 변수  
 `B`  
 선택된 형식을 확인하는 값입니다.  
  
 `T1`  
 B가 true인 경우의 형식 결과입니다.  
  
 `T2`  
 B가 false인 경우의 형식 결과입니다.  
  
## <a name="remarks"></a>설명  
 템플릿 멤버 typedef `conditional<B, T1, T2>::type` 는 `T1` 가 `B` 로 확인될 때 `true`으로 확인되고, `T2` 가 `B` 로 확인될 때 `false`로 확인됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)



