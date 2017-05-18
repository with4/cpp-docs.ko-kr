---
title: "make_signed 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- make_signed
- type_traits/std::make_signed
dev_langs:
- C++
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: 43b41b7016faeb593af12d01f940c27d00882b9e
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="makesigned-class"></a>make_signed 클래스
형식을 만들거나 형식의 크기보다 크거나 같은 부호가 있는 가장 작은 형식을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 수정할 형식입니다.  
  
## <a name="remarks"></a>설명  
 형식 한정자의 인스턴스는 `is_signed<T>`가 true일 때 `T`인 수정된 형식을 가집니다. 그렇지 않은 경우 가장 작은 부호 없는 형식 `UT`이며, 여기서 `sizeof (T) <= sizeof (UT)`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)




