---
title: "심각한 오류 C1191 | Microsoft Docs"
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
  - "C1191"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1191"
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1191
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전역 범위에서만 'dll'을\(를\) 가져올 수 있습니다.  
  
 \/clr 프로그래밍을 사용하는 프로그램에 mscorlib.dll을 가져오는 명령은 네임스페이스나 함수에 표시할 수 없습니다. 전역 범위에서 표시해야 합니다.  
  
 다음 샘플에서는 C1191 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```