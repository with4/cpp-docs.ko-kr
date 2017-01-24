---
title: "인라인 어셈블리의 디버깅 및 목록 | Microsoft Docs"
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
  - "__asm 키워드[C++], 디버깅"
  - "버그, __asm 블록"
  - "디버깅[C++], 인라인 어셈블리 코드"
  - "인라인 어셈블리, 디버깅"
  - "인라인 어셈블리, 목록"
  - "소스 수준 디버거"
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 어셈블리의 디버깅 및 목록
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션으로 컴파일하는 경우 인라인 어셈블리 코드가 포함된 프로그램을 소스 수준 디버거를 사용하여 디버깅할 수 있습니다.  
  
 디버거 내에서 C 또는 C\+\+ 및 어셈블리 언어 줄에 중단점을 설정할 수 있습니다.  혼합된 어셈블리 및 소스 모드를 사용하면 어셈블리 코드의 소스와 디스어셈블된 형태를 모두 표시할 수 있습니다.  
  
 여러 어셈블리 명령 또는 소스 언어 문을 한 줄에 배치하면 디버깅에 방해가 될 수 있습니다.  소스 모드에서는 디버거를 사용하여 중단점을 한 줄에 설정할 수 있지만 같은 줄의 개별 문에 설정할 수는 없습니다.  단일 논리 줄로 확장되는 C 매크로로 정의된 `__asm` 블록에도 동일한 원칙이 적용됩니다.  
  
 [\/FAs](../../build/reference/fa-fa-listing-file.md) 컴파일러 옵션을 사용하여 혼합된 소스 및 어셈블리 목록을 만드는 경우 목록에는 각 어셈블리 언어 줄의 소스와 어셈블리 형태가 모두 포함됩니다.  매크로는 목록에서 확장되지 않지만 컴파일 중에는 확장됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)