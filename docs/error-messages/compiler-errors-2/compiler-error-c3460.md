---
title: "컴파일러 오류 C3460 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3460"
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 사용자 정의 형식만 전달할 수 있습니다.  
  
 자세한 내용은 [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3460.cpp // compile with: /LD /clr public ref class R {};  
```  
  
## 예제  
 다음 샘플에서는 C3460을 생성합니다.  
  
```  
// C3460_b.cpp // compile with: /clr /c #using "C3460.dll" [assembly:TypeForwardedTo(int::typeid)];   // C3460 [assembly:TypeForwardedTo(R::typeid)];  
```