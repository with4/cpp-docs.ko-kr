---
title: "is_error_code_enum 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::is_error_code_enum
- is_error_code_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: 65c818260a4da28c3134e7fb9e124993b0200b74
ms.lasthandoff: 02/24/2017

---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum 클래스
[error_code](../standard-library/error-code-class.md) 열거형을 테스트하는 형식 조건자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template <_Enum>
class is_error_code_enum;
```  
  
## <a name="remarks"></a>설명  
 이 [형식 조건자](../standard-library/type-traits.md)의 인스턴스는 `_Enum` 형식이 `error_code` 형식의 개체에 저장하는 데 적합한 열거형 값이면 true입니다.  
  
 사용자 정의 형식의 경우 이 형식에 특수화를 추가할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<system_error>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)




