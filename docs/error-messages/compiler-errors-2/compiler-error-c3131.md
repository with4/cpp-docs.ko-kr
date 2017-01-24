---
title: "컴파일러 오류 C3131 | Microsoft Docs"
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
  - "C3131"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3131"
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3131
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로젝트에는 'name' 속성이 있는 'module' 특성이 있어야 합니다.  
  
 [module](../../windows/module-cpp.md) 특성에는 이름 매개 변수가 있어야 합니다.  
  
 다음 샘플에서는 C3131 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3131.cpp  
[emitidl];  
[module];   // C3131  
// try the following line instead  
// [module (name="MyLib")];  
  
[public]  
typedef long int LongInt;  
```