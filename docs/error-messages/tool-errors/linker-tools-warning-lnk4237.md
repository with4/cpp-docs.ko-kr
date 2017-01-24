---
title: "링커 도구 경고 LNK4237 | Microsoft Docs"
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
  - "LNK4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4237"
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'dll'에서 가져올 때 \/SUBSYSTEM:NATIVE가 지정되었습니다. \/SUBSYSTEM:CONSOLE 또는 \/SUBSYSTEM:WINDOWS를 사용하십시오.  
  
 다음 중 하나 이상을 직접 사용하는 Windows\(Win32\) 응용 프로그램을 빌드할 때 [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md)가 지정되었습니다.  
  
-   kernel32.dll  
  
-   gdi32.dll  
  
-   user32.dll  
  
-   msvcrt\* dll 중 하나  
  
 이 경고를 해결하려면 **\/SUBSYSTEM:NATIVE**를 지정하지 마십시오.