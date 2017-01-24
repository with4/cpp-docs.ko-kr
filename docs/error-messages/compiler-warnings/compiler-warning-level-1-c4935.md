---
title: "컴파일러 경고(수준 1) C4935 | Microsoft Docs"
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
  - "C4935"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4935"
ms.assetid: a36c56d3-571a-44dd-bb0f-bcc6b020e134
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4935
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

어셈블리 액세스 지정자가 'access'에서 변경되었습니다.  
  
 형식의 어셈블리 표시 유형이 수정되었습니다. 컴파일러는 마지막으로 발견한 지정자를 사용합니다. 예를 들어 정방향 선언의 어셈블리 표시 유형은 클래스 정의의 어셈블리 표시 유형과 다를 수 있습니다.  
  
 C4935는 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C4935를 생성합니다.  
  
```  
// C4935.cpp // compile with: /clr:oldSyntax /W1 /c public __gc public class X {   // C4935 int i; };  
```