---
title: "alloca | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 2b209335-e3a0-4934-93f0-3b5925d22918
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# alloca
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[\_alloca](../c-runtime-library/reference/alloca.md)를 사용하려면 16바이트 맞춤이어야 하고 프레임 포인터를 사용해야 합니다.  
  
 할당된 스택에서는 이후 호출되는 함수의 매개 변수를 위해 아래에 공간을 포함해야 합니다. 자세한 내용은 [스택 할당](../build/stack-allocation.md)을 참조하십시오.  
  
## 참고 항목  
 [스택 사용](../build/stack-usage.md)