---
title: "컴파일러 경고 (수준 1) C4382 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4382
dev_langs:
- C++
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 4571fe618b0ae89251d2748fbbcdfcb654201054
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4382"></a>컴파일러 경고(수준 1) C4382
'type' 척: __clrcall 소멸자 또는 복사 생성자는 형식 /clr에서 낼 수 있습니다: 순수 모듈  
  
 **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않습니다.  
  
 로 컴파일하는 경우 **/clr** (하지 **/clr: 순수**), 예외 처리를 네이티브 형식에 멤버 함수에 필요한 [__cdecl](../../cpp/cdecl.md) 아닌 [__clrcall](../../cpp/clrcall.md)합니다. 멤버 함수를 사용 하 여 네이티브 형식은 `__clrcall` 호출 규칙으로 컴파일된 모듈에서 포착 없습니다 **/clr**합니다.  
  
 로 컴파일된 모듈에서 예외는 발생 하는 경우 **/clr: pure**,이 경고를 무시할 수 있습니다.  
  
 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4382 경고가 발생 합니다.  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```
