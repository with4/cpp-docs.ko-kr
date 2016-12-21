---
title: "컴파일러 오류 C2632 | Microsoft Docs"
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
  - "C2632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2632"
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' 다음에 'type2'이\(가\) 올 수 없습니다.  
  
 이 오류는 두 형식 지정자 사이에 코드가 누락된 경우 발생할 수 있습니다.  
  
 다음 샘플에서는 C2632 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 이 오류는 또한 Visual Studio .NET 2003에서 컴파일러 규칙에 따른 작업을 수행한 결과로 발생할 수 있습니다.  `bool`은 이제 적절한 형식입니다.  이전 버전에서는 `bool`이 형식 정의였으므로 이 이름으로 식별자를 만들 수 있었습니다.  
  
 다음 샘플에서는 C2632 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 이 오류를 해결하여 Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 되도록 하려면 식별자 이름을 바꾸십시오.