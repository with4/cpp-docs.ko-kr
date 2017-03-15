---
title: "예외 처리에서의 타이밍: 요약 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "예외 처리, 타이밍"
  - "처리기, 예외 순서"
  - "시퀀스"
  - "시퀀스, 처리기"
  - "SETJMP.H"
  - "SETJMPEX.H"
  - "구조적 예외 처리, 타이밍"
  - "종료 처리기, 타이밍"
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 예외 처리에서의 타이밍: 요약
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

종료 처리기는 `__try` 문 블록이 종료되는 방법과 관계없이 실행됩니다.  `__try` 블록 밖으로의 점프, 제어를 블록 밖으로 전송하는 `longjmp` 문, 예외 처리로 인한 스택 해제 등이 원인입니다.  
  
> [!NOTE]
>  Visual C\+\+는 `setjmp` 및 `longjmp` 문의 두 가지 형태를 지원합니다.  빠른 버전은 종료 처리를 건너뛰지만 더 효율적입니다.  이 버전을 사용하려면 SETJMP.H 파일을 포함하십시오.  다른 버전은 이전 단락에 설명된 대로 종료 처리를 지원합니다.  이 버전을 사용하려면 SETJMPEX.H 파일을 포함하십시오.  빠른 버전의 성능 향상 정도는 하드웨어 구성에 따라 달라집니다.  
  
 운영 체제는 다른 코드를 실행하기 전에 예외 처리기의 본문을 포함한 모든 종료 처리기를 적절한 순서대로 실행합니다.  
  
 예외로 인해 중단된 경우 시스템은 먼저 예외 처리기 하나 이상의 필터 부분을 실행한 다음 무엇을 종료할지 결정해야 합니다.  이벤트의 순서는 다음과 같습니다.  
  
1.  예외가 발생합니다.  
  
2.  시스템이 활성 예외 처리기의 계층 구조를 보고 우선 순위가 가장 높은 처리기\(블록 및 함수 호출과 관련하여 가장 최근에 설치되고 가장 깊게 중첩된 예외 처리기\)의 필터를 실행합니다.  
  
3.  이 필터가 제어를 전달하는 경우\(0을 반환함\) 제어를 전달하지 않는 필터가 발견될 때까지 프로세스가 계속됩니다.  
  
4.  이 필터가 –1을 반환하는 경우 예외가 발생한 위치에서 실행이 계속되고 종료가 발생하지 않습니다.  
  
5.  필터가 1을 반환하는 경우 다음 이벤트가 발생합니다.  
  
    -   시스템이 현재 실행 중인 코드\(예외가 발생한 코드\)와 제어를 획득하는 예외 처리기가 포함된 스택 프레임 사이의 모든 스택 프레임을 지우며 스택을 해제합니다.  
  
    -   스택이 해제되면서 스택의 각 종료 처리기가 실행됩니다.  
  
    -   예외 처리기 자체가 실행됩니다.  
  
    -   코드 줄에서 이 예외 처리기 끝 다음으로 제어가 전달됩니다.  
  
## 참고 항목  
 [종료 처리기 작성](../cpp/writing-a-termination-handler.md)   
 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)