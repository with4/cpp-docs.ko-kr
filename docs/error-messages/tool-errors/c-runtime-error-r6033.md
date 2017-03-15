---
title: "C 런타임 오류 R6033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6033"
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# C 런타임 오류 R6033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

네이티브 코드를 초기화하는 동안 이 어셈블리에서 MSIL 코드를 사용하려고 합니다.이것은 응용 프로그램에 버그가 있음을 나타냅니다.대개 이러한 오류는 네이티브 생성자 또는 DllMain에서 MSIL 컴파일\(\/clr\) 함수를 호출할 때 발생합니다.  
  
 이 진단 메시지는 로드 잠금 과정에서 MSIL 명령을 실행했음을 의미합니다.  자세한 내용은 [혼합형 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)을 참조하십시오.