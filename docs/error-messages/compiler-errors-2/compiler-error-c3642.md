---
title: "컴파일러 오류 C3642 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3642
dev_langs: C++
helpviewer_keywords: C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4b5d73344b99a42dfc4caf2b9f6b8cf7c9dc18bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3642"></a>컴파일러 오류 C3642
' return_type/args ': __clrcall 호출 규칙이 네이티브 코드에서 사용 하는 함수를 호출할 수 없습니다  
  
 로 표시 된 함수는 [__clrcall](../../cpp/clrcall.md) 호출 규칙의 네이티브 (비관리) 코드에서 호출할 수 없습니다.  
  
 *return_type/args* 는 함수의 이름 또는 유형의 `__clrcall` 함수를 호출 하려고 합니다.  형식에는 함수 포인터를 통해 호출할 때 사용 됩니다.  
  
 네이티브 컨텍스트에서 관리 되는 함수를 호출 하려면 호출 하는 "래퍼" 함수를 추가할 수 있습니다는 `__clrcall` 함수입니다. 또는 CLR 마샬링 메커니즘; 사용할 수 있습니다. 참조 [하는 방법: PInvoke를 사용 하 여 함수 포인터 마샬링](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) 자세한 정보에 대 한 합니다.  
  
 다음 샘플에서는 C3642 오류가 생성 됩니다.  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```