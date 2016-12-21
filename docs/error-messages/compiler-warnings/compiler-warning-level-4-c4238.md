---
title: "컴파일러 경고 (수준 4) C4238 | Microsoft Docs"
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
  - "C4238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4238"
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 클래스 rvalue를 lvalue로 사용했습니다.  
  
 이전 버전의 Visual C\+\+와 호환되도록 하려면 Microsoft 확장\(**\/Ze**\)을 사용하십시오. 그러면 해당 주소를 암시적 또는 명시적으로 가져오는 컨텍스트에서 클래스 형식을 rvalue로 사용할 수 있습니다.  그러나 이와 같이 사용하는 것은 일부 경우에서 다음 예제와 같이 위험할 수도 있습니다.  
  
## 예제  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 이러한 사용은 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서 오류를 발생시킵니다.