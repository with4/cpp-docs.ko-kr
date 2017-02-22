---
title: "컴파일러 경고 (수준 1) C4103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4103"
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' : \#pragma pack\(pop\)이 없어서 헤더를 포함한 후 맞춤 방식이 변경되었습니다.  
  
 압축은 클래스의 레이아웃에 영향을 줍니다. 일반적으로 헤더 파일 간에 압축이 변경되면 문제가 발생할 수 있습니다.  
  
 이 경고를 해결하려면 헤더 파일 마지막에 \#pragma [pack](../../preprocessor/pack.md)\(pop\)을 사용합니다.  
  
 다음 샘플에서는 C4103 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 두 번째 코드 파일:  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```