---
title: "링커 도구 오류 LNK1302 | Microsoft Docs"
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
  - "LNK1302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1302"
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1302
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

안전한 .netmodule만 링크할 수 있습니다.  .netmodule파일을 링크할 수 없습니다.  
  
 사용자가 MSIL 링크를 호출하기 위해 netmodule\(**\/LN**으로 컴파일\)을 링커에 전달했습니다.  **\/clr:safe**를 사용하여 컴파일한 C\+\+ 모듈에 대해서만 MSIL 링크를 사용할 수 있습니다.  
  
 이 오류를 해결하려면 MSIL 링크를 사용할 수 있도록 **\/clr:safe**로 컴파일하거나, 모듈 대신 **\/clr** 또는 **\/clr:pure** .obj 파일을 링커에 전달합니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [\/LN\(MSIL 모듈 만들기\)](../../build/reference/ln-create-msil-module.md)  
  
-   [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)