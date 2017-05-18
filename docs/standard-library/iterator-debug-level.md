---
title: "_ITERATOR_DEBUG_LEVEL | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
dev_langs:
- C++
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
caps.latest.revision: 6
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
ms.sourcegitcommit: 441f493d8ada3ef232f60d917dc3f95812ba9114
ms.openlocfilehash: d5f89f871f60827d894aa414e12b52f0c5f7ef38
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL
`_ITERATOR_DEBUG_LEVEL` 매크로는 [확인된 반복기](../standard-library/checked-iterators.md) 및 [디버그 반복기 지원](../standard-library/debug-iterator-support.md)이 사용되는지 여부를 제어합니다. 이 매크로는 이전 `_SECURE_SCL` 및 `_HAS_ITERATOR_DEBUGGING` 매크로의 기능을 대체하고 결합합니다.  
  
## <a name="macro-values"></a>매크로 값  
다음 표에는 `_ITERATOR_DEBUG_LEVEL` 매크로에 가능한 값이 요약되어 있습니다.  
  
|컴파일 모드|매크로 값|설명|  
|----------------------|----------------|-----------------|  
|**디버그**|||  
||0|확인된 반복기와 반복기 디버깅을 사용하지 않도록 설정합니다.|  
||1|확인된 반복기를 사용하도록 설정하고 반복기 디버깅을 사용하지 않도록 설정합니다.|  
||2(기본값)|반복기 디버깅을 사용하도록 설정하며 확인된 반복기는 관련이 없습니다.|  
|**릴리스**|||  
||0(기본값)|확인된 반복기를 사용하지 않도록 설정합니다.|  
||1|확인된 반복기를 사용하도록 설정하며 반복기 디버깅은 관련이 없습니다.|  
  
릴리스 모드에서 `_ITERATOR_DEBUG_LEVEL`을 2로 지정하면 컴파일러에서 오류가 발생합니다.  
  
## <a name="remarks"></a>설명  
`_ITERATOR_DEBUG_LEVEL` 매크로는 [확인된 반복기](../standard-library/checked-iterators.md)가 사용되는지 여부를 제어하며 디버그 모드에서는 [디버그 반복기 지원](../standard-library/debug-iterator-support.md)이 사용되는지 여부를 제어합니다. `_ITERATOR_DEBUG_LEVEL`이 1 또는 2로 정의된 경우 확인된 반복기는 컨테이너의 경계를 덮어쓰지 않도록 합니다. `_ITERATOR_DEBUG_LEVEL`이 0인 경우 반복기는 확인되지 않습니다. `_ITERATOR_DEBUG_LEVEL`이 1로 정의된 경우 안전하지 않은 반복기 사용으로 인해 런타임 오류가 발생하고 프로그램이 종료됩니다. `_ITERATOR_DEBUG_LEVEL`이 2로 정의된 경우 안전하지 않은 반복기 사용으로 인해 어설션 및 런타임 오류 대화 상자가 표시되며 디버거를 중단할 수 있습니다. 

`_ITERATOR_DEBUG_LEVEL` 매크로는 `_SECURE_SCL` 및 `_HAS_ITERATOR_DEBUGGING` 매크로와 유사한 기능을 지원하므로 특정 상황에서 사용할 매크로 및 매크로 값이 확실하지 않을 수 있습니다. 혼동을 방지하려면 `_ITERATOR_DEBUG_LEVEL` 매크로만 사용하는 것이 좋습니다. 다음 표에서는 기존 코드의 다양한 `_SECURE_SCL` 및 `_HAS_ITERATOR_DEBUGGING` 값에 사용할 해당 `_ITERATOR_DEBUG_LEVEL` 매크로 값에 대해 설명합니다.  
  
|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0(릴리스 기본값)|0(사용 안 함)|0(사용 안 함)|
|1|1(사용)|0(사용 안 함)|
|2(디버그 기본값)|(관련 없음)|1(디버그 모드에서 사용)|
  
확인된 반복기에 대한 경고를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)을 참조하세요.  
  
### <a name="example"></a>예제  
  
`_ITERATOR_DEBUG_LEVEL` 매크로에 대한 값을 지정하려면 [/D](../build/reference/d-preprocessor-definitions.md) 컴파일러 옵션을 사용하여 명령줄에서 정의하거나, C++ 표준 라이브러리 헤더를 소스 파일에 포함하기 전에 `#define`을 사용하세요. 예를 들어 명령줄에서 *sample.cpp*를 디버그 모드에서 컴파일하고 디버그 반복기 지원을 사용하려면 `_ITERATOR_DEBUG_LEVEL` 매크로 정의를 지정할 수 있습니다.  
  
`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`  
  
소스 파일에서 반복기를 정의하는 표준 라이브러리 헤더 앞에 매크로를 지정합니다.  
  
```cpp  
// sample.cpp  
  
#define _ITERATOR_DEBUG_LEVEL 1  
  
#include <vector>  
  
// ...
```  
  
## <a name="see-also"></a>참고 항목  
[확인된 반복기](../standard-library/checked-iterators.md)   
[디버그 반복기 지원](../standard-library/debug-iterator-support.md)   
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)

