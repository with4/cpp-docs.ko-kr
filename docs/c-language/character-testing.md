---
title: "문자 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
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
ms.openlocfilehash: ca3c90169a3dab061a1e50e838b3432deec77b0c
ms.lasthandoff: 04/01/2017

---
# <a name="character-testing"></a>문자 테스트
**ANSI 4.3.1** `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint` 및 `isupper` 함수에서 테스트한 문자의 집합  
  
 다음 목록에서는 Microsoft C 컴파일러에 의해 구현되는 이러한 함수에 대해 설명합니다.  
  
|함수|다음에 대해 테스트|  
|--------------|---------------|  
|`isalnum`|문자 0 - 9, A-Z, a-z ASCII 48-57, 65-90, 97-122|  
|`isalpha`|문자 A-Z, a-z ASCII 65-90, 97-122|  
|`iscntrl`|ASCII 0 -31, 127|  
|`islower`|문자 a-z ASCII 97-122|  
|`isprint`|문자 A-Z, a-z, 0 - 9, 문장 부호, 공백 ASCII 32-126|  
|`isupper`|문자 A-Z ASCII 65-90|  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)
