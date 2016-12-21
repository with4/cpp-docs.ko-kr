---
title: "컴파일러 경고 (수준 1) C4716 | Microsoft Docs"
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
  - "C4716"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4716"
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4716
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function'은\(는\) 값을 반환해야 합니다.  
  
 주어진 함수에서 값을 반환하지 않습니다.  
  
 void 반환 형식을 사용하는 함수에서만 반환 값 없이 return 명령을 사용할 수 있습니다.  
  
 이 함수가 호출될 때에는 정의되지 않은 값이 반환됩니다.  
  
 이 경고는 자동으로 오류가 됩니다.  이 동작을 수정하려면 [\#pragma warning](../../preprocessor/warning.md)을 사용하십시오.  
  
 다음 샘플에서는 C4716 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```