---
title: "컴파일러 오류 C3887 | Microsoft Docs"
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
  - "C3887"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3887"
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3887
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 리터럴 데이터 멤버에 대한 이니셜라이저는 상수 식이어야 합니다.  
  
 [리터럴](../../windows/literal-cpp-component-extensions.md) 데이터 멤버는 상수 식으로만 초기화될 수 있습니다.  
  
 다음 샘플에서는 C3887 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3887.cpp  
// compile with: /clr  
ref struct Y1 {  
   static int i = 9;  
   literal  
   int staticConst = i;   // C3887  
};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3887b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal  
   int staticConst = 9;  
};  
```