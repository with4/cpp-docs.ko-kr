---
title: "컴파일러 오류 C2872 | Microsoft Docs"
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
  - "C2872"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2872"
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2872
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : 모호한 기호입니다.  
  
 컴파일러가 참조되고 있는 기호를 확인할 수 없습니다.  
  
 C2872는 헤더 파일에 [using 지시문](../../misc/using-directive-cpp.md)이 포함되어 있고 이후의 헤더 파일에 대해 `#include`를 실행하여 `using` 지시문에서 지정한 네임스페이스에도 있는 형식이 이 파일에 포함된 경우 발생할 수 있습니다.  `using` 지시문은 `#include`를 사용하여 헤더 파일을 모두 지정한 후에 지정해야 합니다.  
  
 C2872에 대한 더 많은 정보를 위해 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;316317](http://support.microsoft.com/default.aspx?scid=kb;en-us;316317)을 참조하십시오.  
  
 다음 샘플에서는 C2872 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```