---
title: "2.6.5 flush Directive | Microsoft Docs"
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
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.5 flush Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**플러시** 지시문을 명시적 또는 묵시적 "크로스 스레드" 시퀀스 위치에 구현 되어 필요한 팀의 모든 스레드가 특정 개체 \(아래에 메모리 지정\)의 일관 된 보기를 가질 수 있도록 지정 합니다.  따라서 이러한 개체를 참조 하는 식에 대 한 이전 평가 완료 되 고 다음 계산 아직 시작 되지 않은.  예를 들어, 컴파일러는 개체의 값을 레지스터에서 메모리를 복원 해야 하 고 하드웨어 메모리에 쓰기 버퍼 플러시 및 메모리에서 개체의 값을 다시 로드 해야 합니다.  
  
 구문에는  **플러시** 지시문은 다음과 같습니다:  
  
```  
#pragma omp flush [(variable-list)]  new-line  
```  
  
 동기화 해야 하는 개체를 모든 변수에서 지정할 수 있습니다 경우 이러한 변수를 선택적으로 지정할 수 있습니다  *변수 목록*.  포인터가 있을 경우는  *변수 목록*는 포인터가 참조 하는 개체가 아닌, 포인터 자체가 플러시됩니다.  
  
 A  **플러시** 지시문 없이  *변수 목록* 액세스할 수 없는 개체를 제외한 모든 공유 객체를 자동 저장 기간을 동기화 합니다.  \(이 보다 더 많은 오버 헤드가 있을 수 있습니다는  **플러시** 에 있는  *변수 목록*.\) A  **플러시** 지시문 없이  *변수 목록* 에 다음 지시문이 포함 됩니다.  
  
-   `barrier`  
  
-   항목 수 및 종료 로부터  **중요 한**  
  
-   에 입력 및 종료에서 시`ordered`  
  
-   항목 수 및 종료 로부터  **병렬**  
  
-   At 종료 로부터  **에 대 한**  
  
-   At 종료 로부터  **섹션**  
  
-   At 종료 로부터  **단일**  
  
-   항목 수 및 종료 로부터  **에 대 한 병렬**  
  
-   항목 수 및 종료 로부터  **병렬 구역**  
  
 지시문의 경우 내포 되지 않은 한 `nowait` 절 존재입니다.  유의 해야 하는  **플러시** 지시문 중 하나에 대 한 암시 됩니다지 않습니다:  
  
-   항목에  **에 대 한**  
  
-   항목을 또는 출구에서  **마스터**  
  
-   항목에  **섹션**  
  
-   항목에  **단일**  
  
 동작 하는 것 처럼에 대 한 참조는 volatile로 한정 된 형식 개체의 값에 액세스 하는  **플러시** 이전 시퀀스 위치에 해당 개체를 지정 하는 지시문입니다.  동작 하는 것 처럼에 대 한 참조는 volatile로 한정 된 형식 개체의 값을 수정에  **플러시** 지시문 다음 시퀀스 지점에서 해당 개체를 지정 합니다.  
  
 **플러시** 지시문 구문으로 C 언어 명령문에 없습니다, 프로그램 내에서 위치에 일부 제한이 있습니다.  참조 하십시오  [부록 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) 형식 문법에 대 한.  다음 예제에서는 이러한 제한을 보여 줍니다.  
  
```  
/* ERROR - The flush directive cannot be the immediate  
*          substatement of an if statement.  
*/  
if (x!=0)  
   #pragma omp flush (x)  
...  
  
/* OK - The flush directive is enclosed in a  
*      compound statement  
*/  
if (x!=0) {  
   #pragma omp flush (x)  
}  
```  
  
 제한에는  **플러시** 지시어는 다음과 같습니다.  
  
-   지정 된 변수를  **플러시** 지시문 참조 형식이 되었습니다.