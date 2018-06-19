---
title: 전처리기에 대한 지시문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 711e28a569cefbb500a98ab33cd22c527a5fd7c5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382905"
---
# <a name="directives-to-the-preprocessor"></a>전처리기에 대한 지시문
"지시문"은 컴파일 전에 프로그램의 텍스트에서 특정 작업을 수행하도록 C 전처리기에 지시합니다. [전처리기 지시문](../preprocessor/preprocessor-directives.md)은 *전처리기 참조*에 자세히 설명되어 있습니다. 이 예제에서는 전처리기 지시문 `#define`을 사용합니다.  
  
```  
#define MAX 100  
```  
  
 이 문은 컴파일 전에 컴파일러가 `MAX`에 의한 `100`의 발생을 각각 교체하도록 합니다. C 컴파일러 전처리기 지시문은 다음과 같습니다.  
  
|#define|#endif|#ifdef|#line|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**#ifndef**|**#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## <a name="see-also"></a>참고 항목  
 [원본 파일 및 원본 프로그램](../c-language/source-files-and-source-programs.md)