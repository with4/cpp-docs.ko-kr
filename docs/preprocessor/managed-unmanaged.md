---
title: "관리되는, 관리되지 않는 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.unmanaged"
  - "managed_CPP"
  - "unmanaged_CPP"
  - "vc-pragma.managed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "관리되는 pragma"
  - "pragma, 관리"
  - "pragma, 관리되지 않는"
  - "관리되지 않는 pragma"
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 관리되는, 관리되지 않는
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수를 관리되거나 관리되지 않는 것으로 컴파일하기 위해 함수 수준 제어를 사용하도록 설정합니다.  
  
## 구문  
  
```  
  
        #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## 설명  
 [\/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션은 함수를 관리되거나 관리되지 않는 것으로 컴파일하기 위한 모듈 수준 제어를 제공합니다.  
  
 관리되지 않는 함수는 네이티브 플랫폼용으로 컴파일되고 프로그램의 해당 부분을 실행하면 공용 언어 런타임에 의해 네이티브 플랫폼으로 전달됩니다.  
  
 함수는 **\/clr**이 사용되는 경우 기본적으로 관리되는 것으로 컴파일됩니다.  
  
 다음 pragma를 적용할 때  
  
-   함수 본문 내부가 아니라 함수 앞에 pragma를 추가합니다.  
  
-   `#include` 문 다음에 pragma를 추가합니다.  이러한 pragma를 `#include` 문 앞에는 사용하지 않도록 합니다.  
  
 컴파일러는 `managed`이 컴파일에서 사용되지 않는 경우 `unmanaged` 및 **\/clr** pragma를 무시합니다.  
  
 템플릿 함수가 인스턴스화되는 경우 템플릿 정의 시점의 pragma 상태에 따라 함수가 관리되는지 아니면 관리되지 않는지가 결정됩니다.  
  
 자세한 내용은 [혼합형 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md)를 참조하세요.  
  
## 예제  
  
```  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
  **In managed function.  In unmanaged function.**    
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)