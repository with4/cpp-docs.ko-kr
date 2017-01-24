---
title: "컴파일러 경고 (수준 3) C4398 | Microsoft Docs"
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
  - "C4398"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4398"
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4398
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : appdomain이 여러 개 있으면 프로세스별 전역 개체가 제대로 동작하지 않습니다. \_\_declspec\(appdomain\)를 사용해 보십시오.  
  
 [\_\_clrcall](../../cpp/clrcall.md) 호출 규칙이 적용된 가상 함수를 네티이브 형식에 사용하면 응용 프로그램별로 도메인 vtable이 작성됩니다.  여러 응용 프로그램 도메인에 사용하는 경우 그와 같은 변수가 올바르지 않을 수 있습니다.  
  
 기본적으로 각 응용 프로그램 도메인에 대해 전역 변수를 만드는 **\/clr:pure**를 사용하여 컴파일하거나 변수를 명시적으로 `__declspec(appdomain)`으로 표시하여 이 경고를 해결할 수 있습니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [응용 프로그램 도메인 및 Visual C\+\+](../../dotnet/application-domains-and-visual-cpp.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4398 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```