---
title: "컴파일러 오류 C2743 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2743
dev_langs: C++
helpviewer_keywords: C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f45e7617bbf162c23994897c42aab44abeacea88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2743"></a>컴파일러 오류 C2743
'type': __clrcall 소멸자 또는 복사 생성자와 네이티브 형식을 catch 할 수 없습니다  
  
 모듈을 사용 하 여 컴파일된 **/clr** 네이티브 형식 및 해당 형식의 소멸자 또는 복사 생성자 사용 하는 경우 예외를 catch 하려고 했습니다. `__clrcall` 호출 규칙입니다.  
  
 로 컴파일하는 경우 **/clr**, 예외 처리를 네이티브 형식에 멤버 함수에 필요한 [__cdecl](../../cpp/cdecl.md) 아닌 [__clrcall](../../cpp/clrcall.md)합니다. 멤버 함수를 사용 하 여 네이티브 형식은 `__clrcall` 호출 규칙으로 컴파일된 모듈에서 발생 함 없습니다 **/clr**합니다.  
  
 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2743 오류가 발생 합니다.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```