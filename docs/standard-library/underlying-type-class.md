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
- underlying_type
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
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 95012fdeb3ac78d5e1cc76e03ed851a0b9701f5e
ms.lasthandoff: 02/24/2017

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




