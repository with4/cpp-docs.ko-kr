---
title: "2.6.3 barrier Directive | Microsoft Docs"
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
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.3 barrier Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

해당  **장벽** 지시문은 팀 내의 모든 스레드를 동기화 합니다.  다른 모든이 시점에 도달 했습니다 때까지 발생 하는 경우 팀의 각 스레드에서가 기다립니다.  구문에는  **장벽** 지시문은 다음과 같습니다:  
  
```  
#pragma omp barrier new-line  
```  
  
 장애물은 팀의 모든 스레드가 발생 한 후 동시에 장벽 지시문 뒤의 문 실행 팀의 각 스레드에서 시작 됩니다.  **장벽** 지시문 구문으로 C 언어 명령문에 없습니다, 프로그램 내에서 위치에 일부 제한이 있습니다.  참조 하십시오  [부록 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) 형식 문법에 대 한.  다음 예제에서는 이러한 제한을 보여 줍니다.  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```