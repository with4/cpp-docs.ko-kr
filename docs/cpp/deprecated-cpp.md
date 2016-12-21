---
title: "사용되지 않음 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "deprecated"
  - "deprecated_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], deprecated"
  - "deprecated __declspec 키워드"
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 사용되지 않음 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\(Microsoft 전용\) 아래에 설명된 예외를 제외하고, **deprecated** 선언은 [deprecated](../preprocessor/deprecated-c-cpp.md) pragma와 동일한 기능을 제공합니다.  
  
-   **deprecated** 선언을 사용하면 특정 형태의 함수 오버로드를 사용되지 않는 것으로 지정할 수 있습니다. 반면에 pragma 형태는 모든 오버로드된 형태의 함수 이름에 적용됩니다.  
  
-   **deprecated** 선언을 사용하면 컴파일 타임에 표시될 메시지를 지정할 수 있습니다.  메시지의 텍스트는 매크로에서 제공될 수 있습니다.  
  
-   매크로는 **deprecated** pragma를 사용해서만 사용되지 않는 것으로 표시될 수 있습니다.  
  
 컴파일러가 사용되지 않는 식별자의 사용을 발견하는 경우 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 경고가 발생합니다.  
  
## 예제  
 다음 샘플에서는 함수를 사용되지 않는 것으로 표시하는 방법과 사용되지 않는 함수가 사용되는 경우 컴파일 타임에 표시될 메시지를 지정하는 방법을 보여 줍니다.  
  
```  
// deprecated.cpp  
// compile with: /W3  
#define MY_TEXT "function is deprecated"  
void func1(void) {}  
__declspec(deprecated) void func1(int) {}  
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}  
__declspec(deprecated(MY_TEXT)) void func3(int) {}  
  
int main() {  
   func1();  
   func1(1);   // C4996  
   func2(1);   // C4996  
   func3(1);   // C4996  
}  
```  
  
## 예제  
 다음 샘플에서는 클래스를 사용되지 않는 것으로 표시하는 방법과 사용되지 않는 클래스가 사용되는 경우 컴파일 타임에 표시될 메시지를 지정하는 방법을 보여 줍니다.  
  
```  
// deprecate_class.cpp  
// compile with: /W3  
struct __declspec(deprecated) X {  
   void f(){}  
};  
  
struct __declspec(deprecated("** X2 is deprecated **")) X2 {  
   void f(){}  
};  
  
int main() {  
   X x;   // C4996  
   X2 x2;   // C4996  
}  
```  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)