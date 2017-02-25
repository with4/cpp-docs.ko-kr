---
title: "심각한 오류 C1076 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1076"
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 심각한 오류 C1076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 내부 힙 한계에 도달했습니다. \/Zm을 사용하여 한계를 더 높게 지정하십시오.  
  
 템플릿 인스턴스화나 기호가 너무 많은 경우 이 오류가 발생할 수 있습니다.  
  
 이 오류를 해결하려면  
  
1.  [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) 옵션을 사용하여 컴파일러 메모리 제한을 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) 오류 메시지에 지정된 값으로 설정합니다.  [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]에서 이 값을 설정하는 방법 등의 자세한 내용은 [\/Zm\(메모리 할당 제한 지정\)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)의 설명 단원을 참조하십시오.  
  
2.  64비트 운영 체제에서 32비트로 호스팅된 컴파일러를 사용하는 경우 64비트로 호스팅된 컴파일러를 대신 사용하십시오.  자세한 내용은 [방법: 명령줄에서 64비트 Visual C\+\+ 도구 집합 활성화](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)을 참조하십시오.  
  
3.  필요 없는 포함 파일을 제거합니다.  
  
4.  예를 들어, 대형 배열을 선언하는 대신에 메모리를 동적으로 할당하여 필요 없는 전역 변수를 제거합니다.  
  
5.  사용되지 않는 선언을 제거합니다.  
  
6.  대형 함수를 좀 더 작은 함수로 분할합니다.  
  
7.  대형 클래스를 좀 더 작은 클래스로 분할합니다.  
  
8.  현재 파일을 좀 더 작은 여러 개의 파일로 분할합니다.  
  
 빌드가 시작된 후에 바로 C1076이 발생하면 **\/Zm**에 지정된 값이 프로그램에 대해 너무 높기 때문일 수 있습니다.  **\/Zm** 값을 낮추십시오.