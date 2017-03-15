---
title: "안전한 라이브러리: C++ 표준 라이브러리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
dev_langs:
- C++
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 704101f267c1d63ffc5def918f031bfc9b257e67
ms.lasthandoff: 02/24/2017

---
# <a name="safe-libraries-c-standard-library"></a>안전한 라이브러리: C++ 표준 라이브러리
C++ 표준 라이브러리를 포함하여 보안을 강화하기 위해 Visual C++와 함께 제공되는 라이브러리의 여러 가지 기능이 향상되었습니다.  
  
 C++ 표준 라이브러리의 일부 메서드는 버퍼 오버런이나 다른 코드 오류가 발생시킬 수 있기 때문에 잠재적으로 안전하지 않은 것으로 식별되었습니다. 이러한 메서드는 사용하지 않는 것이 좋으며, 이러한 메서드를 대체하기 위해 보다 안전한 새 메서드를 만들었습니다. 이러한 새 메서드는 모두 `_s`로 끝납니다.  
  
 반복기와 알고리즘도 보다 안전하게 만들기 위해 여러 가지 기능이 향상되었습니다. 자세한 내용은 [확인된 반복기](../standard-library/checked-iterators.md), [디버그 반복기 지원](../standard-library/debug-iterator-support.md) 및 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 다음 표에는 안전하지 않을 수 있는 C++ 표준 라이브러리 메서드 및 그에 해당하는 보다 안전한 메서드가 나열되어 있습니다.  
  
|잠재적으로 안전하지 않은 메서드|보다 안전한 메서드|  
|-------------------------------|----------------------|  
|[basic_string::copy](../standard-library/basic-string-class.md#basic_string__copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#basic_string___copy_s)|  
|[char_traits::copy](../standard-library/char-traits-struct.md#char_traits__copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#char_traits___copy_s)|  
  
 위의 안전하지 않을 수 있는 메서드 중 하나를 호출하거나 반복기를 잘못 사용하면 컴파일러에서 [컴파일러 경고(수준 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)을 생성합니다. 이러한 경고를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)를 참조하세요.  
  
## <a name="in-this-section"></a>단원 내용  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [확인된 반복기](../standard-library/checked-iterators.md)  
  
 [디버그 반복기 지원](../standard-library/debug-iterator-support.md)  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)


