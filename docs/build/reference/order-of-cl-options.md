---
title: "CL 옵션 순서 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 옵션 설정"
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# CL 옵션 순서
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL 명령줄에서는 위치에 관계 없이 옵션을 사용할 수 있습니다. 그러나 \/link 옵션은 맨 마지막에 사용해야 합니다.  컴파일러는 [CL 환경 변수](../../build/reference/cl-environment-variables.md)에 지정된 옵션을 먼저 처리한 다음 왼쪽에서 오른쪽으로 명령줄을 읽으면서 차례로 명령 파일을 처리합니다.  모든 옵션은 명령줄에 있는 모든 파일에 적용됩니다.  CL에서 충돌하는 옵션이 있으면 맨 오른쪽에 있는 옵션을 사용합니다.  
  
## 참고 항목  
 [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)