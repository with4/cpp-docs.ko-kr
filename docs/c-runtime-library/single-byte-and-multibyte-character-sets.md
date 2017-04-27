---
title: "싱글바이트 및 멀티바이트 문자 집합 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.character.multibyte
dev_langs:
- C++
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: 8
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: c7d9a62c2b6dc69f9fcd86c8f498e42ce31cae84
ms.lasthandoff: 04/01/2017

---
# <a name="single-byte-and-multibyte-character-sets"></a>싱글바이트 및 멀티바이트 문자 집합
ASCII 문자 집합은 0x00 - 0x7F 범위의 문자를 정의합니다. 주로 유럽의 많은 문자 집합은 ASCII 문자 집합과 동일하게 0x00 - 0x7F 범위 내 문자를 정의할 뿐만 아니라 0x80 - 0xFF 범위의 확장명 문자 집합도 정의합니다. 따라서 ASCII 문자 집합은 물론 많은 유럽 언어의 문자 집합을 표현하는 데에는 8비트의 `SBCS`(싱글바이트 문자 집합)만으로도 충분합니다. 그러나 한국어와 같은 일부 비유럽 문자 집합에는 싱글바이트 코드 구성표로 표현할 수 있는 것보다 더 많은 문자가 있기 때문에 `MBCS`(멀티바이트 문자 집합) 인코딩이 필요합니다.  
  
> [!NOTE]
>  대부분 Microsoft 런타임 라이브러리의 `SBCS` 루틴에서 멀티바이트 바이트, 문자 및 문자열을 적절하게 처리합니다. 많은 멀티바이트 문자 집합은 ASCII 문자 집합을 하위 집합으로 정의합니다. 많은 멀티바이트 문자 집합에서 0x00 - 0x7F 범위의 각 문자는 ASCII 문자 집합에 동일한 값을 가진 문자와 같습니다. 예를 들어 `ASCII` 및 `MBCS` 문자열 모두에서 1바이트 `NULL` 문자('\0')는 값 0x00을 가지며 종료 null 문자를 나타냅니다.  
  
 멀티바이트 문자 집합은 1바이트 문자와 2바이트 문자 모두로 구성할 수 있습니다. 따라서 멀티바이트 문자열은 싱글바이트 및 더블바이트 문자를 혼합하여 포함할 수 있습니다. 2바이트 멀티바이트 문자는 후행 바이트와 선행 바이트를 가집니다. 특정 멀티바이트 문자 집합에서 선행 바이트는 후행 바이트와 마찬가지로 특정 범위 내에 속합니다. 이러한 범위가 겹치는 경우에는 지정된 바이트가 선행 바이트 또는 후행 바이트로 작동하는지 여부를 특정 상황에 따라 판단해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [국제화](../c-runtime-library/internationalization.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)
