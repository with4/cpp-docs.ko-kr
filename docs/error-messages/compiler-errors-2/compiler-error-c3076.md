---
title: "컴파일러 오류 C3076 | Microsoft Docs"
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
  - "C3076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3076"
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'instance' : 참조 형식 'type'의 인스턴스는 네이티브 형식에 포함할 수 없습니다.  
  
 네이티브 형식은 CLR 형식의 인스턴스를 포함할 수 없습니다.  
  
 자세한 내용은 [참조 형식에 대한 C\+\+ 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3076 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3076.cpp  
// compile with: /clr /c  
ref struct U {};  
  
struct V {  
   U y;   // C3076  
};  
  
ref struct W {  
   U y;   // OK  
};  
```