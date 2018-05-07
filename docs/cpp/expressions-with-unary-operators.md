---
title: 단항 연산자가 있는 식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e1b8db2e02e6ab3e2a70d94ba5f6fe3516e464e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="expressions-with-unary-operators"></a>단항 연산자가 있는 식
단항 연산자는 하나의 식에서 하나의 피연산자에 대해서만 작동합니다. 단항 연산자의 종류는 다음과 같습니다.  
  
-   [간접 참조 연산자 (*)](../cpp/indirection-operator-star.md)  
  
-   [주소 연산자 (&)](../cpp/address-of-operator-amp.md)  
  
-   [단항 더하기 연산자 (+)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [단항 부정 연산자 (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [논리 부정 연산자 (!)](../cpp/logical-negation-operator-exclpt.md)  
  
-   [1의 보수 연산자 (~)](../cpp/one-s-complement-operator-tilde.md)  
  
-   [후 위 증가 연산자 (+ +)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [전위 감소 연산자 (-)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [캐스트 연산자)](../cpp/cast-operator-parens.md)  
  
-   [sizeof 연산자](../cpp/sizeof-operator.md)  
  
-   [__uuidof 연산자](../cpp/uuidof-operator.md)  
  
-   [__alignof 연산자](../cpp/alignof-operator.md)  
  
-   [New 연산자](../cpp/new-operator-cpp.md)  
  
-   [delete 연산자](../cpp/delete-operator-cpp.md)  
  
 이러한 연산자는 오른쪽에서 왼쪽으로 결합됩니다. 단항 식은 일반적으로 후위 식 또는 주 식 앞에 오는 구문을 포함합니다.  
  
 다음은 단항 식의 가능한 형식입니다.  
  
-   *postfix-expression*  
  
-   `++` *단항 식*  
  
-   `--` *단항 식*  
  
-   *단항 연산자* *캐스트 식*  
  
-   `sizeof` *단항 식*  
  
-   `sizeof(` *형식 이름* `)`  
  
-   `decltype(` *식* `)`  
  
-   *할당 식*  
  
-   *할당 취소 식*  
  
 모든 *후 위 식* 것으로 간주 됩니다는 *단항 식*, 모든 기본 식으로 간주 하기 때문에 및는 *후 위 식*, 모든 기본 식 것으로 간주 한 *단항 식* 도 합니다. 자세한 내용은 참조 [후 위 식](../cpp/postfix-expressions.md) 및 [기본 식](../cpp/primary-expressions.md)합니다.  
  
 A *단항 연산자* 다음 기호 중 하나 이상의 구성 됩니다. `* & + - ! ~`  
  
 *캐스트 식* 은 단항 식 유형을 변경 하는 선택적 캐스팅을 사용 합니다. 자세한 내용은 참조 [캐스트 연산자: ()](../cpp/cast-operator-parens.md)합니다.  
  
 *식* 식일 수 있습니다. 자세한 내용은 참조 [식](../cpp/expressions-cpp.md)합니다.  
  
 *할당 식* 참조 하는 `new` 연산자입니다. *할당 취소 식* 참조 하는 `delete` 연산자입니다. 자세한 내용은 이 항목의 앞부분에 나오는 링크를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [식의 형식](../cpp/types-of-expressions.md)