---
title: _SECURE_SCL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9e2bfb1095c28ea3592c5af2b89cb2fbeddcb60c
ms.openlocfilehash: f3712b4417c0fed972d9a20b6d82479561cce4b0
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="securescl"></a>_SECURE_SCL
  
[확인된 반복기](../standard-library/checked-iterators.md)가 사용하도록 설정되었는지를 정의하는 이 매크로는 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)로 교체되었습니다. 확인된 반복기는 기본적으로 디버그 빌드에서는 사용하도록 설정되고 정품 빌드에서는 사용하지 않도록 설정됩니다.  
  
> [!IMPORTANT]
> `_SECURE_SCL` 매크로는 더 이상 직접 사용할 수는 없습니다. 대신 `_ITERATOR_DEBUG_LEVEL`을 사용하여 확인된 반복기 설정을 제어합니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
  
확인된 반복기를 사용하는 경우에는 안전하지 않은 반복기 사용으로 인해 런타임 오류가 발생하며 프로그램이 종료됩니다. 확인된 반복기를 사용하도록 설정하려면 `_ITERATOR_DEBUG_LEVEL`을 1 또는 2로 설정합니다. 이 값은 `_SECURE_SCL` 설정 1(사용)과 동일합니다.  
  
```  
#define _ITERATOR_DEBUG_LEVEL 1  
```  
  
확인된 반복기를 사용하지 않도록 설정하려면 `_ITERATOR_DEBUG_LEVEL`을 0으로 설정합니다. 이 값은 `_SECURE_SCL` 설정 0(사용 안 함)과 동일합니다.  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
확인된 반복기에 대한 경고를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
[확인된 반복기](../standard-library/checked-iterators.md)   
[디버그 반복기 지원](../standard-library/debug-iterator-support.md)   
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)


