---
title: "컴파일러 오류 C3898 | Microsoft Docs"
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
  - "C3898"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3898"
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3898
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 형식 데이터 멤버는 관리되는 형식의 멤버만 될 수 있습니다.  
  
 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버를 네이티브 클래스에 선언했습니다.  `initonly` 데이터 멤버는 CLR 클래스에서만 선언할 수 있습니다.  
  
 다음 샘플에서는 C3898 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3898.cpp  
// compile with: /clr  
struct Y1 {  
   initonly  
   static int data_var = 9;   // C3898  
};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3898b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int data_var = 9;  
};  
```