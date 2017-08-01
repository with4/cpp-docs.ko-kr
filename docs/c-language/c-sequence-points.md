---
title: "C 시퀀스 위치 | Microsoft Docs"
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
- sequence points
ms.assetid: c84885a5-4336-4eba-a643-058df4249903
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 85e9d8c04280b6f40081b1362a46bf27b62bcc28
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="c-sequence-points"></a>C 시퀀스 위치
연속 "시퀀스 위치" 사이에서 개체의 값은 식에 의해 한 번만 수정될 수 있습니다. C 언어는 다음과 같은 시퀀스 위치를 정의합니다.  
  
-   논리 AND 연산자(**&&**)의 왼쪽 피연산자. 계속하기 전에 논리 AND 연산자의 왼쪽 피연산자가 완전히 평가되고 모든 파생 작업이 완료됩니다. 왼쪽 피연산자가 false(0)로 평가되는 경우 다른 피연산자는 평가되지 않습니다.  
  
-   논리 OR 연산자(`||`)의 왼쪽 피연산자. 계속하기 전에 논리 OR 연산자의 왼쪽 피연산자가 완전히 평가되고 모든 파생 작업이 완료됩니다. 왼쪽 피연산자가 true(0이 아님)로 평가되는 경우 다른 피연산자는 평가되지 않습니다.  
  
-   쉼표 연산자의 왼쪽 피연산자. 계속하기 전에 쉼표 연산자의 왼쪽 피연산자가 완전히 평가되고 모든 파생 작업이 완료됩니다. 쉼표 연산자의 두 피연산자는 항상 계산됩니다. 함수 호출에서 쉼표 연산자는 평가 순서를 보장하지 않습니다.  
  
-   함수 호출 연산자. 함수 진입 전에 함수에 대한 모든 인수가 계산되고 모든 파생 작업이 완료됩니다. 인수 사이의 계산 순서는 지정되어 있지 않습니다.  
  
-   조건 연산자의 첫째 피연산자. 계속하기 전에 조건 연산자의 첫 번째 피연산자가 완전히 평가되고 모든 파생 작업이 완료됩니다.  
  
-   전체 초기화 식(즉, 선언문의 초기화 끝과 같이 다른 식의 일부가 아닌 식)의 끝  
  
-   식 문의 식. 식 문은 선택적 식과 세미콜론(**;**)으로 구성됩니다. 식은 해당 파생 작업에 대해 계산되며 이 계산 다음에 시퀀스 위치가 있습니다.  
  
-   선택(**if** 또는 `switch`) 문의 제어 식. 선택에 종속된 코드가 실행되기 전에 식이 완전히 계산되고 모든 파생 작업이 완료됩니다.  
  
-   `while` 또는 **do** 문의 제어 식. `while` 또는 **do** 루프의 다음 반복에 있는 문이 실행되기 전에 식이 완전히 계산되고 모든 파생 작업이 완료됩니다.  
  
-   **for** 문의 세 가지 식 각각. **for** 루프의 다음 반복에 있는 문이 실행되기 전에 식이 완전히 계산되고 모든 파생 작업이 완료됩니다.  
  
-   `return` 문의 식. 호출 함수로 제어가 반환되기 전에 식이 완전히 계산되고 모든 파생 작업이 완료됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [식 계산](../c-language/expression-evaluation-c.md)
