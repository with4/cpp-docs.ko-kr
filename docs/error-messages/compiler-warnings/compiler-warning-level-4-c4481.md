---
title: "컴파일러 경고 (수준 4) C4481 | Microsoft Docs"
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
  - "C4481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4481"
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용되었습니다. 'keyword' 지정자를 재정의합니다.  
  
 C\+\+ 표준이 아닌 키워드가 사용되었습니다. 이러한 키워드에는 \/clr에서도 사용할 수 있는 재정의 지정자가 있습니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
-   [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Override 지정자](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## 예제  
 다음 샘플에서는 C4481 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```