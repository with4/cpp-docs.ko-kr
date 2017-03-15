---
title: "링커 도구 경고 LNK4224 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4224"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4224"
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 링커 도구 경고 LNK4224
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

option은\(는\) 더 이상 지원되지 않습니다. 무시됩니다.  
  
 사용되지 않는 잘못된 링커 옵션이 지정되었으므로 무시됩니다.  
  
 예를 들어 .obj에서 \/comment 지시문이 나타나는 경우 LNK4224가 발생할 수 있습니다.  \/comment 지시문은 더 이상 사용되지 않는 exestr 옵션을 사용하여 [주석](../../preprocessor/comment-c-cpp.md) pragma를 통해 추가되었을 가능성이 큽니다.  dumpbin [\/ALL](../../build/reference/all.md)을 사용하여 .obj 파일에 있는 링커 지시문을 확인하십시오.  
  
 가능한 경우 해당 .obj에 대한 소스를 수정하여 pragma를 제거하십시오.  이 경고를 무시하면 **\/clr:pure**로 컴파일된 .executable이 예상한 대로 실행되지 않을 수 있습니다.  
  
## 예제  
 다음 샘플에서는 LNK4224가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```