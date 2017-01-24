---
title: "컴파일러 경고 (수준 1) C4288 | Microsoft Docs"
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
  - "C4288"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4288"
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4288
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨 : 'var' : for 루프에서 선언된 루프 제어 변수가 for 루프 범위 외부에서 사용되어 외부 범위에 있는 선언과 충돌합니다.  
  
 [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 **\/Zc:forscope\-**를 사용하여 컴파일할 때 **for** 루프에서 선언한 변수를 [for](../../cpp/for-statement-cpp.md) 루프 범위 뒤에 사용했습니다.  C\+\+ 언어의 Microsoft 확장에서는 이 변수를 범위에 남아 있도록 하고 C4288을 발생시켜 첫 번째 변수을 사용하지 않았다는 것을 표시합니다.  
  
 \/Ze를 통해 **for** 루프에서의 Microsoft 확장을 지정하는 방법에 대한 자세한 내용은 [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)를 참조하십시오.  
  
 다음 샘플에서는 C4288 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```