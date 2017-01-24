---
title: "컴파일러 경고(수준 4) C4434 | Microsoft Docs"
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
  - "C4434"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4434"
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4434
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정적 생성자의 액세스 가능성은 private여야 합니다. private 액세스로 변경합니다.  
  
 C4434는 컴파일러가 정적 생성자의 액세스 가능성을 변경했음을 나타냅니다.  정적 생성자는 공용 언어 런타임에서 호출하기 위한 것이므로 그 액세스 가능성은 private여야 합니다.  자세한 내용은 다음을 참조하십시오. [정적 생성자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).  
  
## 예제  
 다음 샘플에서는 C4434 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4434.cpp  
// compile with: /W4 /c /clr  
public ref struct R {  
   static R(){}   // C4434  
};  
```