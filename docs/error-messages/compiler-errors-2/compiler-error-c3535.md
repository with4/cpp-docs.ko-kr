---
title: "컴파일러 오류 C3535 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3535
dev_langs: C++
helpviewer_keywords: C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ab054ceefa51ab944e2d048996e25559b0c86ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3535"></a>컴파일러 오류 C3535
'type1'에서 'type2'에 대 한 형식을 추론할 수 없습니다.  
  
 으로 선언 된 변수의 형식을 `auto` 초기화 식의 형식에서 키워드를 추론할 수 없습니다. 초기화 식으로 계산 하는 경우이 오류가 발생 하는 예를 들어 `void`는 형식이 아닙니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  초기화 식의 형식이 아닌지 확인 `void`합니다.  
  
2.  선언 기본 형식에 대 한 포인터 인지 확인 합니다. 자세한 내용은 참조 [기본 형식을](../../cpp/fundamental-types-cpp.md)합니다.  
  
3.  선언 형식에 대 한 포인터 이면 초기화 식이 인지 확인 포인터 형식입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 C3535 초기화 식의 결과가 `void`합니다.  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>예제  
 문은 변수를 선언 하므로 다음 예제에서는 생성 C3535 `x` 이니셜라이저의 형식을 하지만 추론된 된 형식에 대 한 포인터 식이 double입니다. 따라서 컴파일러는 변수의 형식을 추론할 수 없습니다.  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 C3535 때문에 변수 `p` 추론된 된 형식에 대 한 포인터를 선언 하지만 초기화 식은 포인터 형식이 아닙니다.  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)   
 [기본 형식](../../cpp/fundamental-types-cpp.md)