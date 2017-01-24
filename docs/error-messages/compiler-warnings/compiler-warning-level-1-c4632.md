---
title: "컴파일러 경고 (수준 1) C4632 | Microsoft Docs"
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
  - "C4632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4632"
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML 문서 주석: file \- 액세스가 거부되었습니다. reason  
  
 .xdc 파일\(`file`\)의 경로가 올바르지 않으므로 .xdc 파일이 생성되지 않았습니다.  
  
 다음 샘플에서는 C4632 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4632.cpp  
// compile with: /clr /docv:\\falsedir /LD /W1  
// C4632 expected  
  
/// Text for class MyClass.  
public ref class MyClass {};  
```