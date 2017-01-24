---
title: "컴파일러 오류 C3162 | Microsoft Docs"
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
  - "C3162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3162"
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 소멸자가 있는 참조 형식은 정적 데이터 멤버 'member'의 형식으로 사용할 수 없습니다.  
  
 클래스에 정적 멤버 함수도 포함되어 있는 경우 공용 언어 런타임에서 사용자 정의 소멸자를 실행할 시기를 결정할 수 없습니다.  
  
 개체를 명시적으로 삭제하지 않으면 소멸자가 실행되지 않습니다.  
  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [일반적인 Visual C\+\+ 64비트 마이그레이션 문제](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## 예제  
 다음 샘플에서는 C3162 오류가 발생하는 경우를 보여 줍니다.  
  
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