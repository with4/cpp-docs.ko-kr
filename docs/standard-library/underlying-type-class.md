---
title: "underlying_type 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 8d5af1b1115d2845fcfa4dbd89dc3776e7e66ccf
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="underlyingtype-class"></a>underlying_type 클래스
열거형 형식에 대한 내부 정수 계열 형식을 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
struct underlying_type;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 수정할 형식입니다.  
  
## <a name="remarks"></a>설명  
 템플릿 클래스의 `type` 구성원 형식 정의는 `T`가 열거형 형식이면 `T`의 기본 정수 계열 형식 이름을 지정합니다. 그렇지 않은 경우에는 구성원 형식 정의 `type`이 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)




