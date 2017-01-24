---
title: "x86 컴파일러와 충돌 | Microsoft Docs"
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
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# x86 컴파일러와 충돌
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

4 바이트보다 큰 데이터 형식은 x86 컴파일러를 사용하여 응용 프로그램을 컴파일할 때 자동으로 스택에 정렬되지 않습니다.  x86 컴파일러의 아키텍처는 4바이트 정렬된 스택이기 때문에 4바이트보다 큰\(예: 64비트 정수\) 정수는 8바이트 주소에 자동으로 정렬할 수 없습니다.  
  
 정렬되지 않은 데이터로 작업하는 데는 두 가지 의미가 있습니다.  
  
-   정렬된 위치에 액세스하는 데 걸리는 시간보다 정렬되지 않은 위치에 액세스하는 데 시간이 오래 걸릴 수 있습니다.  
  
-   정렬되지 않은 위치는 연동된 작업에 사용할 수 없습니다.  
  
 더 엄격한 맞춤이 필요한 경우에만 `__declspec(align(N)) on your variable declarations`를 사용하십시오.  이렇게 하면 컴파일러가 사양에 맞게 스택을 동적으로 정렬하게 됩니다.  그러나 스택을 런타임에 동적으로 조정하면 응용 프로그램의 실행 속도가 느려질 수 있습니다.  
  
## 참고 항목  
 [형식 및 저장소](../build/types-and-storage.md)   
 [맞춤](../cpp/align-cpp.md)