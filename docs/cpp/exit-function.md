---
title: "exit 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit 함수"
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# exit 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

표준 포함 파일인 STDLIB.H에서 선언된 **exit** 함수는 C\+\+ 프로그램을 종료합니다.  
  
 **exit**에 대한 인수로 제공되는 값은 프로그램의 반환 코드 또는 종료 코드로서 운영 체제로 반환됩니다.  규칙에 따라 반환 코드 0은 프로그램이 성공적으로 완료되었음을 의미합니다.  
  
> [!NOTE]
>  프로그램의 성공 또는 실패를 나타내기 위해 STDLIB.H에 정의된 상수 `EXIT_FAILURE` 및 `EXIT_SUCCESS`를 사용할 수 있습니다.  
  
 **main** 함수에서 `return` 문을 실행하는 것은 해당 함수의 인수로서 반환 값을 사용하여 **exit** 함수를 호출하는 것과 같습니다.  
  
 자세한 내용은 런타임 라이브러리 참조에서 [exit](../c-runtime-library/reference/exit-exit-exit.md)를 참조하십시오.  
  
## 참고 항목  
 [프로그램 종료](../cpp/program-termination.md)