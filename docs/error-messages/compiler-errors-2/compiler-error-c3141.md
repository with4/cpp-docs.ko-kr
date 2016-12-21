---
title: "컴파일러 오류 C3141 | Microsoft Docs"
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
  - "C3141"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3141"
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3141
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface\_name' : 인터페이스는 공용 상속만 지원합니다.  
  
 [interface \(or \_\_interface\)](../../cpp/interface.md) 키워드를 사용하여 정의한 인터페이스는 공용 상속만 지원합니다.  
  
 다음 샘플에서는 C3141 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3141.cpp  
__interface IBase {};  
__interface IDerived1 : protected IBase {};  // C3141  
__interface IDerived2 : private IBase {};    // C3141  
```