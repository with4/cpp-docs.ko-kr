---
title: "alignment_of 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- alignment_of
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
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
ms.openlocfilehash: dee638b0260deff1d8701353c7119fc1b0082685
ms.lasthandoff: 02/24/2017

---
# <a name="alignmentof-class"></a>alignment_of 클래스
지정된 형식의 맞춤을 가져옵니다. 이 구조체는 [alignof](../cpp/alignof-and-alignas-cpp.md) 측면에서 구현됩니다. 맞춤 값을 쿼리만 하면 되는 경우 `alignof`를 직접 사용합니다. 태그 디스패치를 수행하는 경우처럼 정수 계열 상수가 필요한 경우 alignment_of를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Ty>
struct alignment_of;
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 쿼리는 `Ty` 형식의 맞춤 값을 보유합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [aligned_storage 클래스](../standard-library/aligned-storage-class.md)

