---
title: "종료 처리기에 대한 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "제한 사항, 종료 처리기"
  - "종료 처리기, 제한 사항"
  - "try-catch 키워드[C++], 종료 처리기"
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 종료 처리기에 대한 제한
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`goto` 문을 사용하여 `__try` 문 블록 또는 `__finally` 문 블록으로 점프할 수 없습니다.  대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. 그러나 `__try` 문 블록 밖으로 점프할 수 있습니다. 또한 `__finally` 블록 안에 예외 처리기나 종료 처리기를 중첩시킬 수 없습니다.  
  
 또한 종료 처리기에 허용되는 몇 종류의 코드는 그 결과가 불확실하기 때문에 주의하여 사용해야 합니다\(있는 경우\).  그 중 하나는 `__finally` 문 블록 밖으로 점프하는 `goto` 문입니다.  블록이 정상적인 종료의 일부분으로 실행되는 경우 비정상적인 일이 생기지 않지만  시스템이 스택을 해제하는 경우 해제가 중지되고 비정상적인 종료가 없는 것처럼 현재 함수가 제어권을 갖습니다.  
  
 `__finally` 문 블록 안에 `return` 문을 사용해도 상황이 거의 같습니다.  종료 처리기를 포함하는 함수의 직접 실행 호출자에게 제어가 반환됩니다.  시스템이 스택을 해제 중이었으면 이 프로세스가 중단되고, 예외가 발생하지 않은 것처럼 프로그램이 계속됩니다.  
  
## 참고 항목  
 [종료 처리기 작성](../cpp/writing-a-termination-handler.md)   
 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)