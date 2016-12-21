---
title: "함수 형식 | Microsoft Docs"
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
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 함수 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본적으로 함수에는 두 가지 형식이 있습니다.  스택 프레임이 필요한 함수를 프레임 함수라고 하고,  스택 프레임이 필요하지 않은 함수를 리프 함수라고 합니다.  
  
 프레임 함수는 스택 공간을 할당하거나, 다른 함수를 호출하거나, 비volatile 레지스터를 저장하거나, 예외 처리를 사용하는 함수입니다.  여기에는 함수 테이블 엔트리도 필요합니다.  프레임 함수에는 프롤로그와 에필로그가 필요합니다.  프레임 함수에서는 스택 공간을 동적으로 할당하고 프레임 포인터를 사용할 수 있습니다.  프레임 함수는 이를 정리할 때 이러한 호출 규칙을 모두 활용할 수 있습니다.  
  
 프레임 함수가 다른 함수를 호출하지 않는 경우 스택을 맞출 필요가 없습니다. 자세한 내용은 [스택 할당](../build/stack-allocation.md)을 참조하십시오.  
  
 리프 함수는 함수 테이블 엔트리가 필요하지 않은 함수입니다.  이 함수에서는 다른 함수를 호출하거나 공간을 할당하거나 비 volatile 레지스터를 저장할 수 없습니다.  이 함수에서는 실행하는 동안 스택이 맞춤되지 않은 상태로 남도록 허용합니다.  
  
## 참고 항목  
 [스택 사용](../build/stack-usage.md)