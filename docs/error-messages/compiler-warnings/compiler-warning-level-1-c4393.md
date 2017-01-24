---
title: "컴파일러 경고 (수준 1) C4393 | Microsoft Docs"
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
  - "C4393"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4393"
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4393
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : const는 리터럴 데이터 멤버에 영향을 주지 않으므로 무시됩니다.  
  
 [리터럴](../../windows/literal-cpp-component-extensions.md) 멤버 데이터 멤버도 const로 지정 했습니다. Const는 리터럴 데이터 멤버 의미 하므로 있습니다 필요가 없습니다 추가 상수를 선언 합니다.  
  
 다음 샘플에서는 C4393 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4393.cpp  
// compile with: /clr /W1 /c  
ref struct Y1 {  
   literal const int staticConst = 10;   // C4393  
   literal int staticConst2 = 10;   // OK  
};  
```