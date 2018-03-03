---
title: "C 키워드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2fd746124cdfc267267bc5d6803700cca507c34d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="c-keywords"></a>C 키워드
"키워드"는 C 컴파일러에서 특별한 의미를 가진 단어입니다. 7번째 및 8번째 변환 단계에서는 식별자가 C 키워드와 같은 철자 및 대/소문자를 사용할 수 없습니다. 자세한 내용은 *전처리기 참조*의 [변환 단계](../preprocessor/phases-of-translation.md) 설명을 참조하세요. 식별자에 대한 자세한 내용은 [식별자](../c-language/c-identifiers.md)를 참조하세요. C 언어는 다음의 키워드를 사용합니다.  
  
|||||  
|-|-|-|-|  
|**auto**|**double**|**int**|**struct**|  
|**break**|**else**|**long**|**switch**|  
|**case**|**enum**|**register**|**typedef**|  
|**char**|**extern**|**return**|**union**|  
|**const**|**float**|**short**|**unsigned**|  
|**continue**|**for**|**signed**|**void**|  
|**default**|**goto**|**sizeof**|**volatile**|  
|**do**|**if**|**static**|**while**|  
  
 키워드는 재정의될 수 없습니다. 그러나 컴파일 전에 C [전처리기 지시문](../preprocessor/preprocessor-directives.md)을 사용하여 키워드를 대체할 텍스트를 지정할 수 있습니다.  
  
 **Microsoft 전용**  
  
 ANSI C 표준을 사용하면 두 개의 선행 밑줄이 쳐진 식별자를 컴파일러의 구현용으로 예약할 수 있습니다. 따라서 Microsoft 규칙은 이중 밑줄이 쳐진 Microsoft 전용 키워드 이름 앞에 있게 됩니다. 이들 단어는 식별자 이름으로 사용할 수 없습니다. 두 개의 밑줄을 사용하는 경우를 포함하여 명명 식별자의 ANSI 규칙에 대한 자세한 내용은 [식별자](../c-language/c-identifiers.md)를 참조하세요.  
  
 Microsoft C 컴파일러에서 다음 키워드 및 특수 식별자가 인식됩니다.  
  
|||||  
|-|-|-|-|  
|**__asm**|**dllimport**2|**__int8**|**naked**2|  
|**__based**1|**__except**|**__int16**|**__stdcall**|  
|**__cdecl**|**__fastcall**|**__int32**|**thread**2|  
|**__declspec**|**__finally**|**__int64**|**__try**|  
|**dllexport**2|**__inline**|**__leave**||  
  
 1. **__based** 키워드의 경우 32 비트 및 64 비트 대상 컴파일에서 제한적으로 사용됩니다.  
  
 2. 이들은 **__declspec**과 함께 사용되는 특수 식별자이며 다른 컨텍스트에서의 사용은 제한되지 않습니다.  
  
 Microsoft 확장은 기본적으로 사용하도록 설정됩니다. 프로그램이 완전하게 이식 가능하도록 하려면, 컴파일하는 동안 /Za 옵션(ANSI 호환을 위한 컴파일)을 지정하여 Microsoft 확장을 사용하지 않도록 설정할 수 있습니다. 이렇게 하면 Microsoft 관련 키워드를 사용할 수 없습니다.  
  
 Microsoft 확장을 사용하면 위에 나열된 키워드를 프로그램에서 사용할 수 있습니다. ANSI 규격에 따라 이러한 키워드의 대부분에는 두 개의 밑줄이 앞에 옵니다. 네 가지 예외 사항인 **dllexport**, **dllimport**, **naked** 및 **thread**는 **__declspec**과 함께 사용되므로 선행 밑줄이 필요하지 않습니다. 이전 버전과의 호환성을 위해 나머지 키워드에는 밑줄 한 개가 옵니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [C 요소](../c-language/elements-of-c.md)