---
title: "컴파일러 오류 C3883 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3883"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3883"
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3883
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : initonly 정적 데이터 멤버는 초기화되어야 합니다.  
  
 [initonly](../../dotnet/initonly-cpp-cli.md)로 표시한 변수를 올바르게 초기화하지 않았습니다.  
  
 다음 샘플에서는 C3883 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3883.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   static int staticConst1;   // C3883  
};  
```  
  
 다음 샘플에서는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3883b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int staticConst2 = 0;  
};  
```  
  
 다음 샘플은 정적 생성자에서 초기화하는 방법을 보여 줍니다.  
  
```  
// C3883c.cpp  
// compile with: /clr /LD  
ref struct Y1 {  
   initonly  
   static int staticConst1;  
  
   static Y1() {  
      staticConst1 = 0;  
   }  
};  
```