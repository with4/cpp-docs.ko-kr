---
title: "컴파일러 경고 (수준 4) C4255 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4255"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4255"
ms.assetid: 2087b635-4b4c-4182-8a01-c26770d2bb88
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 4) C4255
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수 프로토타입을 입력하지 않았습니다. '\(\)'에서 '\(void\)'로 변환됩니다.  
  
 컴파일러에서 함수에 대한 명시적 인수 목록을 찾지 못했습니다.  이 경고는 C 컴파일러에서만 발생합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4255 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4255.c  
// compile with: /W4 /WX  
#pragma warning (default : 4255)  
  
void f()  { // C4255  
// try the following line instead  
//void f(void) {  
}  
  
int main(int argc, char *argv[]) {  
   f();  
}  
```