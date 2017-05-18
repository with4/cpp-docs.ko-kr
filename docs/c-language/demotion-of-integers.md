---
title: "정수 강등 | Microsoft Docs"
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
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 468b88ccb64c06e64e9b234188295b3fcc148b1f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="demotion-of-integers"></a>정수 강등
**ANSI 3.2.1.2** 정수를 더 짧은 부호 있는 정수로 변환한 결과 또는 값을 표현할 수 없는 경우 부호 없는 정수를 같은 길이의 부호 있는 정수로 변환한 결과  
  
 **long** 정수를 **a short**로 캐스팅하거나 **short**를 `char`로 캐스팅할 때는 가장 덜 중요한 바이트가 보존됩니다.  
  
 예를 들어, 다음 줄은  
  
```  
short x = (short)0x12345678L;  
```  
  
 0x5678 값을 `x`에 할당하고 다음 줄은  
  
```  
char y = (char)0x1234;  
```  
  
 0x34 값을 `y`에 할당합니다.  
  
 부호 있는 변수가 부호 없는 변수로 변환되거나 그 반대의 경우 비트 패턴이 동일하게 유지됩니다. 예를 들어, -2(0xFE)를 부호 없는 값으로 캐스팅하면 254(0xFE)가 생성됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [정수](../c-language/integers.md)
