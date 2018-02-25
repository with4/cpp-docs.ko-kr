---
title: "is_move_constructible 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15c1fb9b3b4e3dc27b887ac70005be55813399a7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ismoveconstructible-class"></a>is_move_constructible 클래스
형식에 이동 생성자가 있는지 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
struct is_move_constructible;
```  
  
#### <a name="parameters"></a>매개 변수  
 T  
 평가할 형식입니다.  
  
## <a name="remarks"></a>설명  
 이동 작업을 사용하여 `T` 형식을 생성할 수 있는 경우 true로 평가되는 형식 조건자입니다. 이 조건자는 `is_constructible<T, T&&>`과 같습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)



