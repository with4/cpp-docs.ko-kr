---
title: "값 종류: Lvalue 및 Rvalue (Visual c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e06dca827d6b5cb5d457a2eda6aa143bb5d0fe5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="lvalues-and-rvalues-visual-c"></a>Lvalue 및 Rvalue (Visual c + +)
모든 c + + 식에는 형식이 고에 속하는 한 *값 범주*합니다. 값 범주는 컴파일러는 만들기, 복사 및 식 평가 중에 임시 개체를 이동 하는 경우 따라야 하는 규칙 기반으로 합니다. 

 표준 C + + 17에 식 값 범주 다음과 같이 정의합니다.

- A *glvalue* 계산 함수, 개체 또는 비트 필드의 id를 확인 하는 식입니다. 
- A *prvalue* 계산 개체 또는 비트 필드를 초기화 하거나 지정 되어 있으므로 컨텍스트에서 표시 되는 연산자의 피연산자의 값을 계산 하는 식입니다. 
- *xvalue* 개체 또는 비트 필드 (일반적으로 이기 때문에 수명의 끝 부분에서) 해당 리소스를 다시 사용할 수를 나타내는 glvalue 됩니다. [예: rvalue 참조 (8.3.2) 관련 된 식이 특정 종류 xvalues 해당 반환 형식이 rvalue 참조는 함수 호출 또는 rvalue 참조 형식에 캐스팅 등을 생성 합니다. ] 
- *lvalue* 는 xvalue 없는 glvalue 됩니다. 
- *rvalue* 는 prvalue 인지는 xvalue 값입니다. 

다음 다이어그램에서는 범주 간의 관계를 보여 줍니다.

 ![C + + 식 값 범주](media/value_categories.png "c + + 식 값 범주")  
 
 Lvalue에 프로그램에 액세스할 수 있는 주소가 있습니다. Lvalue 식의 예로 변수 이름, 포함 `const` 변수, 배열 요소, 함수는 lvalue 참조, 비트 필드, 공용 구조체 및 클래스 멤버를 반환 하는 호출 합니다. 
 
 Prvalue 식에 프로그램에서 액세스할 수 있는 주소가 없습니다. Prvalue 식의 예로 리터럴, 비참조 형식을 반환 하는 함수 호출 및 컴파일러에 의해서만 액세스할 수 있지만 식 평가 중에 만들어진 임시 개체를 들 수 있습니다. 

 Xvalue 값 식에 게 주소가 있지만 초기화를 rvalue 참조 식에 대 한 액세스를 제공 하는 데 사용할 수 있습니다. 함수 호출으로 반환 하는 rvalue 참조 및 배열 첨자, 멤버 및 포인터 멤버 식은 배열 또는 개체는 rvalue 참조는 있습니다. 
 
 다음 예제에서는 lvalue 및 rvalue에 대한 여러 가지 올바른 사용과 올바르지 않은 사용의 예를 보여 줍니다.  
  
```  
// lvalues_and_rvalues2.cpp  
int main()  
{  
   int i, j, *p;  
  
   // Correct usage: the variable i is an lvalue and the literal 7 is a prvalue.  
   i = 7;  
  
   // Incorrect usage: The left operand must be an lvalue (C2106).  `j * 4` is a prvalue.
   7 = i; // C2106  
   j * 4 = 7; // C2106  
  
   // Correct usage: the dereferenced pointer is an lvalue.  
   *p = i;   
  
   const int ci = 7;  
   // Incorrect usage: the variable is a non-modifiable lvalue (C3892).  
   ci = 9; // C3892  
  
   // Correct usage: the conditional operator returns an lvalue.  
   ((i < 3) ? i : j) = 7;  
}  
```  
  
> [!NOTE]
>  이 항목의 예제는 연산자가 오버로드되지 않을 때 올바른 사용과 올바르지 않은 사용의 예를 보여 줍니다. 연산자를 오버로드하여 `j * 4`와 같은 식을 lvalue로 만들 수 있습니다.  

  
 용어 *lvalue* 및 *rvalue* 주로 개체 참조를 참조할 때 사용 됩니다. 참조에 대 한 자세한 내용은 참조 [Lvalue 참조 선언 자: &](../cpp/lvalue-reference-declarator-amp.md) 및 [Rvalue 참조 선언 자: & &](../cpp/rvalue-reference-declarator-amp-amp.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기본 개념](../cpp/basic-concepts-cpp.md)   
 [Lvalue 참조 선언 자: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)