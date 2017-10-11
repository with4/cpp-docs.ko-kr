---
title: "컴파일러 오류 C3162 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3162
dev_langs:
- C++
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8bfde260ef0efe58ed70469a80a8bf7316eefa46
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3162"></a>컴파일러 오류 C3162
'type': 소멸자가 있는 참조 형식은 정적 데이터 멤버 'member'의 형식으로 사용할 수 없습니다  
  
 공용 언어 런타임 클래스는 정적 멤버 함수에도 포함 되어 있으면 사용자 정의 소멸자를 실행 하는 시기를 알 수 없습니다.  
  
 개체를 명시적으로 삭제 하지 않는 한 소멸자가 실행 되지 않습니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [일반적인 Visual C++ 64비트 마이그레이션 문제](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3162 오류가 발생 합니다.  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```
