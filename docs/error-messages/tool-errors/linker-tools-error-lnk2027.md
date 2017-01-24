---
title: "링커 도구 오류 LNK2027 | Microsoft Docs"
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
  - "LNK2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2027"
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

확인되지 않은 모듈 참조 'module'이\(가\) 있습니다.  
  
 링커에 전달한 파일이 **\/ASSEMBLYMODULE**을 사용하여 지정하지도 링커에 직접 전달하지도 않은 모듈에 종속되어 있습니다.  
  
 LNK2027을 해결하려면 다음 중 하나를 수행하십시오.  
  
-   모듈 종속성이 있는 파일을 링커에 전달하지 마십시오.  
  
-   **\/ASSEMBLYMODULE**을 사용하여 모듈을 지정하십시오.  
  
-   모듈이 안전한.netmodule 인 경우 모듈을 링커에 직접 전달 합니다.  
  
 자세한 내용은 [\/ASSEMBLYMODULE\(MSIL 모듈을 어셈블리에 추가\)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) 및 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)를 참조하십시오.