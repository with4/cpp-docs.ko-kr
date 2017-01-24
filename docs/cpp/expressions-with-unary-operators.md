---
title: "단항 연산자가 있는 식 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "식[C++], 연산자"
  - "식[C++], 단항 연산자"
  - "단항 연산자, 식"
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 단항 연산자가 있는 식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단항 연산자는 하나의 식에서 하나의 피연산자에 대해서만 작동합니다.  단항 연산자의 종류는 다음과 같습니다.  
  
-   [간접 참조 연산자\(\*\)](../cpp/indirection-operator-star.md)  
  
-   [주소 연산자\(&\)](../cpp/address-of-operator-amp.md)  
  
-   [단항 더하기 연산자\(\+\)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [단항 부정 연산자\(–\)](../misc/unary-negation-operator.md)  
  
-   [논리 부정 연산자\(\!\)](../cpp/logical-negation-operator-exclpt.md)  
  
-   [1의 보수 연산자\(~\)](../cpp/one-s-complement-operator-tilde.md)  
  
-   [후위 증가 연산자\(\+\+\)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [후위 감소 연산자\(––\)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [캐스트 연산자\(\)](../cpp/cast-operator-parens.md)  
  
-   [sizeof 연산자](../cpp/sizeof-operator.md)  
  
-   [\_\_uuidof 연산자](../cpp/uuidof-operator.md)  
  
-   [\_\_alignof 연산자](../cpp/alignof-operator.md)  
  
-   [new 연산자](../cpp/new-operator-cpp.md)  
  
-   [delete 연산자](../cpp/delete-operator-cpp.md)  
  
 이러한 연산자는 오른쪽에서 왼쪽으로 결합됩니다.  단항 식은 일반적으로 후위 식 또는 주 식 앞에 오는 구문을 포함합니다.  
  
 다음은 단항 식의 가능한 형식입니다.  
  
-   *postfix\-expression*  
  
-   `++` *unary\-expression*  
  
-   `––` *unary\-expression*  
  
-   *unary\-operator* *cast\-expression*  
  
-   `sizeof` *unary\-expression*  
  
-   `sizeof(` *type\-name* `)`  
  
-   `decltype(` *expression* `)`  
  
-   *allocation\-expression*  
  
-   *deallocation\-expression*  
  
 모든 *postfix\-expression*은 *unary\-expression*으로 간주되는데, 모든 기본 식은 *postfix\-expression*으로 간주되므로 *unary\-expression*으로도 간주됩니다.  자세한 내용은 [후위 식](../cpp/postfix-expressions.md) 및 [기본 식](../cpp/primary-expressions.md)을 참조하십시오.  
  
 *unary\-operator*는 `* &`, `+`, `–`, `!`, `~` 기호 중 하나 이상으로 구성됩니다.  
  
 *cast\-expression*은 형식을 변경하는 선택적 캐스트를 가진 단항 식입니다.  자세한 내용은 [캐스트 연산자: \(\)](../cpp/cast-operator-parens.md)를 참조하십시오.  
  
 *expression*은 모든 식이 될 수 있습니다.  자세한 내용은 [식](../cpp/expressions-cpp.md)을 참조하십시오.  
  
 *allocation\-expression*은 `new` 연산자를 참조합니다.  *deallocation\-expression*은 `delete` 연산자를 참조합니다.  자세한 내용은 이 항목의 앞부분에 나오는 링크를 참조하십시오.  
  
## 참고 항목  
 [식의 형식](../cpp/types-of-expressions.md)