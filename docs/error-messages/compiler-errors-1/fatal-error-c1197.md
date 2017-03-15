---
title: "심각한 오류 C1197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1197"
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 심각한 오류 C1197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'mscorlib.dll\_1'을\(를\) 참조할 수 없습니다. 프로그램에서 이미 'mscorlib.dll\_2'을\(를\) 참조했습니다.  
  
 컴파일러가 공용 언어 런타임의 버전과 일치합니다.  그러나 이전 버전에서 공용 언어 런타임 파일의 버전을 참조하려고 했습니다.  
  
 이 오류를 해결하려면 컴파일에 사용하는 버전의 Visual C\+\+와 함께 제공되는 버전의 공용 언어 런타임에서만 파일을 참조해야 합니다.  
  
## 예제  
 다음 샘플에서는 C1197 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```