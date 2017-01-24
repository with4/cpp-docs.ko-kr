---
title: "/RANGE | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/RANGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RANGE dumpbin 옵션"
  - "-RANGE dumpbin 옵션"
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RANGE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/RAWDATA 또는 \/DISASM과 같은 다른 dumpbin 옵션과 함께 사용된 경우 dumpbin의 출력을 수정합니다.  
  
## 구문  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## Flags  
 **vaMin**  
 dumpbin 작업을 시작할 가상 주소입니다.  
  
 **vaMax**\(선택적 요소\)  
 dumpbin 작업을 끝낼 가상 주소입니다.  주소를 지정하지 않으면 파일 끝까지 dumpbin이 진행됩니다.  
  
## 설명  
 이미지의 가상 주소를 보려면 이미지\(RVA \+ Base\)에 대한 맵 파일을 사용하거나, dumpbin의 **\/DISASM** 또는 **\/HEADERS** 옵션을 사용하거나, Visual Studio 디버거의 디스어셈블리 창을 사용합니다.  
  
## 예제  
 다음 예제에서는 **\/range**를 사용하여 **\/disasm** 옵션의 출력을 수정합니다.  이 예제에서 시작 값은 10진수로, 끝 값은 16진수로 표시됩니다.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)