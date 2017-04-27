---
title: "is_standard_layout 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_standard_layout
- type_traits/std::is_standard_layout
dev_langs:
- C++
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
caps.latest.revision: 16
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
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: 39b7198e020a2c520fb054687a7dadfdd8172826
ms.lasthandoff: 02/24/2017

---
# <a name="isstandardlayout-class"></a>is_standard_layout 클래스
형식이 표준 레이아웃인지 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Ty>
struct is_standard_layout;
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Ty`|쿼리할 형식입니다.|  
  
## <a name="remarks"></a>설명  
 이 형식 조건자의 인스턴스는 `Ty` 형식이 메모리에 표준 레이아웃의 멤버 개체가 있는 클래스인 경우 true이고, 그렇지 않은 경우 false입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)




