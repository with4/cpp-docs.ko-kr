---
title: "malloc 맞춤 | Microsoft Docs"
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
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# malloc 맞춤
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[malloc](../c-runtime-library/reference/malloc.md)는 기본 맞춤이 있는 개체를 저장하도록 적절히 정렬되고 할당된 메모리 크기에 맞출 수 있는 메모리를 반환하도록 보장합니다.  *기본 맞춤*은 맞춤 사양 없이 구현에서 지원되는 가장 큰 맞춤보다 작거나 같은 맞춤입니다. \(Visual C\+\+에서 이는 `double` 또는 8바이트에 필요한 맞춤입니다.  64비트 플랫폼을 대상으로 하는 코드에서 16바이트입니다.\) 예를 들어, 4바이트 할당은 4바이트보다 작은 개체를 지원하는 경계에 정렬됩니다.  
  
 Visual C\+\+에서는 *과도하게 정렬된* 형식으로도 알려진 *확장된 맞춤*을 갖는 형식이 허용됩니다.  예를 들어, SSE 형식 [\_\_m128](../cpp/m128.md)과 `__m256`, 그리고 `__declspec(align(``n``))`을 사용하여 선언된 형식\(여기서 `n`는 8보다 큼\)은 확장된 맞춤을 갖습니다.  확장된 맞춤이 필요한 개체에 대해 적합한 경계에서 메모리 맞춤은 `malloc`에 의해 보증되지 않습니다.  과도하게 정렬된 형식에 대한 메모리를 할당하려면 [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) 및 관련 함수를 사용합니다.  
  
## 참고 항목  
 [스택 사용](../build/stack-usage.md)   
 [맞춤](../cpp/align-cpp.md)   
 [\_\_declspec](../cpp/declspec.md)