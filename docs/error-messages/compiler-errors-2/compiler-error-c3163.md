---
title: "컴파일러 오류 C3163 | Microsoft Docs"
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
  - "C3163"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3163"
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3163
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'construct': 특성이 이전 선언과 일관성이 없습니다.  
  
 정의에 적용된 특성이 선언에 적용된 특성과 충돌합니다.  
  
 C3163을 해결하는 한 가지 방법은 전방 선언의 특성을 제거하는 것입니다.  전방 선언의 특성은 정의의 특성보다 작거나 같아야 합니다.  
  
 C3163 오류의 가능한 원인은 Microsoft SAL\(소스 코드 주석 언어\)과 관련이 있습니다.  **\/analyze** 플래그를 사용하여 프로젝트를 컴파일하지 않으면 SAL 매크로가 확장되지 않습니다.  \/analyze 없이 정상적으로 컴파일되는 프로그램을 \/analyze 옵션을 사용하여 다시 컴파일하는 경우 C3163 오류가 throw될 수 있습니다.  SAL에 대한 자세한 내용은 [SAL 주석](../../c-runtime-library/sal-annotations.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3163 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## 참고 항목  
 [SAL 주석](../../c-runtime-library/sal-annotations.md)