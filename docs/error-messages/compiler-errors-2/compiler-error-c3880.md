---
title: "컴파일러 오류 C3880 | Microsoft Docs"
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
  - "C3880"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3880"
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3880
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 리터럴 데이터 멤버가 될 수 없습니다.  
  
 [literal](../../windows/literal-cpp-component-extensions.md) 특성의 형식은 다음 형식 중 하나이거나 컴파일할 때 다음 형식 중 하나로 변환할 수 있어야 합니다.  
  
-   정수 계열 형식  
  
-   string  
  
-   정수 계열 형식 또는 내부 형식의 열거형  
  
 다음 샘플에서는 C3880 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```