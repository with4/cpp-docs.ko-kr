---
title: "is_error_condition_enum 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::is_error_condition_enum
- std.is_error_condition_enum
- is_error_condition_enum
- system_error/std::is_error_condition_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
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
ms.openlocfilehash: 316e375554d80bfa58dfba537e5c36a881028a20
ms.lasthandoff: 02/24/2017

---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum 클래스
[error_condition](../standard-library/error-condition-class.md) 열거형을 테스트하는 형식 조건자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template <_Enum>
class is_error_condition_enum;
```  
  
## <a name="remarks"></a>설명  
 이 [형식 조건자](../standard-library/type-traits.md)의 인스턴스는 `_Enum` 형식이 `error_condition` 형식의 개체에 저장하는 데 적합한 열거형 값이면 true입니다.  
  
 사용자 정의 형식의 경우 이 형식에 특수화를 추가할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<system_error>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)




