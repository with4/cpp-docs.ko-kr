---
title: "다중 스레드 프로그램으로 문제 영역 방지 | Microsoft Docs"
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
helpviewer_keywords: 
  - "오류[C++], 다중 스레드 프로그램"
  - "다중 스레딩[C++], 문제 해결"
  - "스레딩[C++], 문제 해결"
  - "문제 해결[C++], 다중 스레딩"
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 다중 스레드 프로그램으로 문제 영역 방지
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다중 스레드 C 프로그램을 만들거나 링크 또는 실행할 때 발생할 수 있는 몇 가지 문제점이 있습니다.  다음 표에서는 자주 발생하는 몇 가지 문제에 대해 설명합니다. MFC 관점에서 이와 유사한 논의를 보려면 [다중 스레딩: 프로그래밍 팁](../../parallel/multithreading-programming-tips.md)을 참조하십시오.  
  
|문제점|예상 원인|  
|---------|-----------|  
|프로그램에서 보호 위반이 발생했다는 메시지 상자가 표시됩니다.|많은 Win32 프로그래밍 오류로 인해 보호 위반이 발생합니다.  보호 위반의 일반적인 원인은 null 포인터에 데이터를 간접 할당하기 때문입니다.  결과적으로 프로그램이 자신에게 속하지 않는 메모리에 액세스를 시도하므로 보호 위반이 발생합니다.<br /><br /> 보호 위반의 원인을 쉽게 알아내는 방법은 디버깅 정보를 사용하여 프로그램을 컴파일한 다음 Visual C\+\+ 환경의 디버거에서 프로그램을 실행하는 것입니다.  보호 오류가 발생하는 경우 Windows는 디버거에 컨트롤을 전송하고 문제가 발생한 줄에 커서를 놓습니다.|  
|프로그램에서 컴파일 및 링크 오류가 많습니다.|컴파일러의 경고 수준을 가장 높은 값 중의 하나로 설정하고 경고 메시지에 주의하여 많은 잠재적 문제를 제거할 수 있습니다.  경고 수준 3 또는 경고 수준 4 옵션을 사용하여 실수에 의한 데이터 변환, 함수 프로토타입 누락 및 ANSI에서 지원하지 않는 기능 사용 등을 검색할 수 있습니다.|  
  
## 참고 항목  
 [C 및 Wind32를 사용한 다중 스레딩](../../parallel/multithreading-with-c-and-win32.md)