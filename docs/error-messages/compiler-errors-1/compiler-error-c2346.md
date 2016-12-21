---
title: "컴파일러 오류 C2346 | Microsoft Docs"
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
  - "C2346"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2346"
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2346
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function'을\(를\) 네이티브로 컴파일할 수 없습니다. reason  
  
 컴파일러에서 함수를 MSIL로 컴파일할 수 없습니다.  
  
 자세한 내용은 [관리되는, 관리되지 않는](../../preprocessor/managed-unmanaged.md) 및 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)를 참조하십시오.  
  
### 이 오류를 해결하려면  
  
1.  MSIL로 컴파일할 수 없는 함수의 코드를 제거합니다.  
  
2.  모듈을 **\/clr**로 컴파일하거나 관리되지 않는 pragma를 사용하여 함수를 관리되지 않는 함수로 표시하지 마십시오.  
  
## 예제  
 다음 샘플에서는 C2346 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```