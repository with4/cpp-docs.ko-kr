---
title: "_HAS_ITERATOR_DEBUGGING | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: 7
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
ms.sourcegitcommit: 9e2bfb1095c28ea3592c5af2b89cb2fbeddcb60c
ms.openlocfilehash: 97d899ead2c556a39118dd49bf1f6ac7ef8a9b04
ms.lasthandoff: 02/24/2017

---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING  
  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)로 교체된 이 매크로는 반복기 디버깅 기능이 디버그 빌드에서 사용하도록 설정되었는지 여부를 정의합니다. 반복기 디버깅은 기본적으로 디버그 빌드에서는 사용하도록 설정되고 정품 빌드에서는 사용하지 않도록 설정됩니다. 자세한 내용은 [디버그 반복기 지원](../standard-library/debug-iterator-support.md)을 참조하세요.  
  
> [!IMPORTANT]
> `_HAS_ITERATOR_DEBUGGING` 매크로는 직접 사용되지 않습니다. 대신 `_ITERATOR_DEBUG_LEVEL`을 사용하여 반복기 디버그 설정을 제어합니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
디버그 빌드에서 반복기 디버깅을 사용하도록 설정하려면 `_ITERATOR_DEBUG_LEVEL`을 2로 설정합니다. 이 값은 `_HAS_ITERATOR_DEBUGGING` 설정 1(사용)과 동일합니다.  
  
```  
#define _ITERATOR_DEBUG_LEVEL 2  
```  
  
일반 정품 빌드에서는 `_ITERATOR_DEBUG_LEVEL`을 2로 설정할 수 없고 `_HAS_ITERATOR_DEBUGGING`을 1로 설정할 수 없습니다.  
  
디버그 빌드에서 디버그 반복기를 사용하지 않도록 설정하려면 `_ITERATOR_DEBUG_LEVEL`을 0 또는 1로 설정합니다. 이 값은 `_HAS_ITERATOR_DEBUGGING` 설정 0(사용 안 함)과 동일합니다.  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
## <a name="see-also"></a>참고 항목  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
 [디버그 반복기 지원](../standard-library/debug-iterator-support.md)   
 [확인된 반복기](../standard-library/checked-iterators.md)   
 [안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)


