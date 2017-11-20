---
title: "문자 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89f48346d9b96c7de20c11fd4cbcde106571ed57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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