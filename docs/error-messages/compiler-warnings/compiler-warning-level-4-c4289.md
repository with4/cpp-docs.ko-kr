---
title: "컴파일러 경고 (수준 4) C4289 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4289"
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 4) C4289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨 : 'var' : for 루프에서 선언된 루프 제어 변수가 for 루프 범위 외부에서 사용되었습니다.  
  
 [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 **\/Zc:forScope\-**를 사용하여 컴파일할 때 [for](../../cpp/for-statement-cpp.md) 루프에서 선언한 변수를 **for** 루프 범위 뒤에 사용했습니다.  
  
 **\/Ze**를 사용하여 **for** 루프에서의 표준 동작을 지정하는 방법에 대한 자세한 내용은 [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)를 참조하십시오.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4289 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```