---
title: "컴파일러 경고 (수준 1) C4258 | Microsoft Docs"
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
  - "C4258"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4258"
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4258
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : for 루프의 정의가 무시되고 바깥쪽 범위의 정의가 사용됩니다.  
  
 [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)로 컴파일될 때 [for](../../cpp/for-statement-cpp.md) 루프에 정의된 변수가 **for** 루프 범위를 벗어나 있습니다.  루프 변수와 같은 이름의 변수를 포함 루프 안에 정의한 다음 **for** 루프를 포함하는 범위에서 다시 사용하면 이 경고가 발생합니다.  예를 들면 다음과 같습니다.  
  
```  
// C4258.cpp  
// compile with: /Zc:forScope /W1  
int main()  
{  
   int i;  
   {  
      for (int i =0; i < 1; i++)  
         ;  
      i = 20;   // C4258 i (in for loop) has gone out of scope  
   }  
}  
```