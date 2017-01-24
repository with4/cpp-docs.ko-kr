---
title: "/LINKERMEMBER | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linkermember"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINKERMEMBER dumpbin 옵션"
  - "LINKERMEMBER dumpbin 옵션"
  - "-LINKERMEMBER dumpbin 옵션"
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LINKERMEMBER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINKERMEMBER[:{1|2}]  
```  
  
## 설명  
 이 옵션은 라이브러리에 정의된 공용 기호를 표시합니다.  기호를 오프셋과 함께 개체 순으로 표시하려면 인수 1을 지정합니다.  개체의 오프셋과 인덱스 번호를 표시한 다음 각 개체 인덱스와 함께 사전 순으로 기호를 나열하려면 인수 2를 지정합니다.  두 출력을 모두 표시하려면 번호 인수 없이 \/LINKERMEMBER를 지정합니다.  
  
 [\/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은 [\/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)