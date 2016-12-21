---
title: "컴파일러 오류 C3073 | Microsoft Docs"
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
  - "C3073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3073"
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : ref 클래스에 사용자 정의 복사 생성자가 없습니다.  
  
 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일에서는 컴파일러가 참조 형식에 대한 복사 생성자를 생성하지 않습니다.  **\/clr** 컴파일을 수행할 때 형식의 인스턴스를 복사해야 하는 경우 참조 형식에 대한 고유한 복사 생성자를 직접 정의해야 합니다.  
  
 자세한 내용은 [참조 형식에 대한 C\+\+ 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3073 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3073.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int) {}  
};  
  
ref class S {  
public:  
   S(int) {}  
   S(const S %rhs) {}   // copy constructor  
};  
  
void f(R) {}  
void f2(S) {}  
void f3(R%){}  
  
int main() {  
   R r(1);  
   f(r);   // C3073  
   f3(r);   // OK  
  
   S s(1);  
   f2(s);   // OK  
}  
```