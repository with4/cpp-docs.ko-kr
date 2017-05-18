---
title: "인라인 함수 | Microsoft Docs"
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
- fast code
- inline functions, __inline keyword
- functions [C++], inline functions
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
caps.latest.revision: 10
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: cdcf109b76725855aeb6daae1628bbc6a57e6e32
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="inline-functions"></a>인라인 함수
**Microsoft 전용**  
  
 `__inline` 키워드는 컴파일러가 모든 함수 호출 건에 대해 함수 정의 내에서 코드를 대체하라고 말합니다. 하지만 코드 대체는 컴파일러의 판단하에서만 발생합니다. 예를 들어, 컴파일러는 해당 주소를 가져온 경우나 인라인에 비해 너무 클 경우에는 함수를 인라인하지 않습니다.  
  
 인라이닝의 후보로 간주되는 함수의 경우 새 스타일 함수 정의를 사용해야 합니다.  
  
 이 양식을 사용하여 인라인 함수를 지정합니다.  
  
 `__inline` *type*opt*function-definition*`;`  
  
 인라인 함수를 사용하면 보다 빨리 코드를 생성할 수 있고 동등한 함수 호출이 생성하는 코드보다 더 작은 코드를 생성하는 경우도 있습니다. 그 이유는 다음과 같습니다.  
  
-   함수 호출을 실행하는 데 필요한 시간을 저장합니다.  
  
-   3줄 이하의 작은 인라인 함수는 컴파일러 인수가 인수 및 반환 값을 처리하는 코드를 생성하지 않으므로 해당 함수 호출보다 적은 코드를 만듭니다.  
  
-   인라인으로 생성된 함수에서는 컴파일러가 프로시저 간 최적화를 수행하지 않기 때문에 일반 함수에 사용할 수 없는 코드 최적화가 진행됩니다.  
  
 `__inline`을 사용하는 함수는 인라인 어셈블러 코드와 혼동해서는 안 됩니다. 자세한 내용은 [인라인 어셈블러](../c-language/inline-assembler-c.md)를 참조하세요.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [inline, __inline, \__forceinline](../cpp/inline-functions-cpp.md)


