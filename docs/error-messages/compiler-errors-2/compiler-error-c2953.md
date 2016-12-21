---
title: "컴파일러 오류 C2953 | Microsoft Docs"
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
  - "C2953"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2953"
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2953
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 클래스 템플릿이 이미 정의되었습니다.  
  
 소스 파일을 확인하고 다른 정의에 대한 파일을 포함합니다.  
  
 다음 샘플에서는 C2953을 생성합니다.  
  
```  
// C2953.cpp // compile with: /c template <class T>  class A {}; template <class T>  class A {};   // C2953 template <class T>  class B {};   // OK  
```