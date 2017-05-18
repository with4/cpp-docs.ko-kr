---
title: "컴파일러 경고 (수준 1) C4002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4002
dev_langs:
- C++
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 15bb9910d689cd9b8f05ed6df306f3bdf1f79195
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4002"></a>컴파일러 경고(수준 1) C4002
'identifier' 매크로의 실제 매개 변수가 너무 많습니다.  
  
 매크로의 실제 매개 변수 개수가 매크로 정의의 정식 매개 변수 개수를 초과합니다. 전처리기는 추가 매개 변수를 수집하지만 매크로 확장 중에 무시합니다.  
  
 C 4002 잘못 사용 하는 경우 발생할 수 있습니다 [Variadic 매크로](../../preprocessor/variadic-macros.md)합니다.  
  
 다음 샘플에서는 C4002를 생성합니다.  
  
```  
// C4002.cpp  
// compile with: /W1  
#define test(a) (a)  
  
int main() {  
   int a = 1;  
   int b = 2;  
   a = test(a,b);   // C4002  
   // try..  
   a = test(a);  
}  
```  
  
 이 오류는 Visual Studio .NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로 생성될 수도 있습니다. 더 이상 매크로에 추가 쉼표를 사용할 수 없습니다.  
  
 컴파일러는 매크로의 추가 쉼표를 더 이상 허용하지 않습니다. Visual Studio .NET 2003과 Visual C++의 Visual Studio .NET 버전 둘 다에서 코드가 유효하려면 추가 쉼표를 제거합니다.  
  
```  
// C4002b.cpp  
// compile with: /W1  
#define F(x,y)  
int main()  
{  
   F(2,,,,,,3,,,,,,)   // C4002  
   // Try the following line instead:  
   // F(2,3)  
}  
```
