---
title: "링커 도구 오류 LNK1245 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1245"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1245"
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1245
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'subsystem' 하위 시스템이 잘못 지정되었습니다. \/SUBSYSTEM은 WINDOWS, WINDOWSCE 또는 CONSOLE이어야 합니다.  
  
 다음 조건 중 하나가 참인 상태에서 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)를 사용하여 개체를 컴파일했습니다.  
  
-   링커가 하위 시스템을 유추할 수 없도록 사용자 지정 진입점을 정의했습니다\([\/ENTRY](../../build/reference/entry-entry-point-symbol.md)\).  
  
-   \/clr 개체에 사용할 수 없는 값을 [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 링커 옵션에 전달했습니다.  
  
 두 경우 모두 문제를 해결하려면 \/SUBSYSTEM 링커 옵션에 유효한 값을 지정해야 합니다.