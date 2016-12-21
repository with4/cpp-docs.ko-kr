---
title: "컴파일러 오류 C3821 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3821"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3821"
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3821
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 관리되는 형식 또는 함수는 관리되지 않는 함수에서 사용할 수 없습니다.  
  
 인라인 어셈블리나 [setjmp](../../c-runtime-library/reference/setjmp.md)를 사용하는 함수는 값 형식이나 관리되는 클래스를 포함할 수 없습니다.  이 오류를 해결하려면 인라인 함수 및 `setjmp`를 제거하거나 관리되는 개체를 제거하십시오.  
  
 C3821은 vararg 함수에 자동 저장소를 사용하려는 경우에도 발생할 수 있습니다.  자세한 내용은 [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) 및 [참조 형식에 대한 C\+\+ 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3821 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## 예제  
 다음 샘플에서는 C3821 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  
  
## 예제  
 다음 샘플에서는 C3821 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3821c.cpp  
// compile with: /clr:oldSyntax  
// processor: /x86  
__gc  class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A *a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```