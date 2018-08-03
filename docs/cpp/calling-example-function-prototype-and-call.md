---
title: '호출 예제: 함수 프로토타입 및 호출 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f9ee05b55a0945d18e78dc67df5653c06c8a1bc
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404384"
---
# <a name="calling-example-function-prototype-and-call"></a>호출 예제: 함수 프로토타입 및 호출
## <a name="microsoft-specific"></a>Microsoft 전용  
 다음 예제에서는 다양한 호출 규칙을 사용하여 함수를 호출한 결과를 보여 줍니다.  
  
 이 예제는 다음과 같은 함수 구조를 기반으로 합니다. `calltype`을 적절한 호출 규칙으로 바꾸십시오.  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 자세한 내용은 [호출 예제 결과](../cpp/results-of-calling-example.md)합니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [호출 규칙](../cpp/calling-conventions.md)