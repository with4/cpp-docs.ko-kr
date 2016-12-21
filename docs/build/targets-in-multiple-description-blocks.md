---
title: "여러 개의 설명 블록에 포함된 대상 | Microsoft Docs"
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
  - "블록, 여러 설명"
  - "설명 블록"
  - "여러 설명 블록"
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 여러 개의 설명 블록에 포함된 대상
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

여러 가지 명령을 사용하여 하나의 대상을 하나 이상의 설명 블록에 업데이트하려면 대상과 종속 파일 사이에 두 개의 인접한 콜론\(::\)을 지정합니다.  
  
```  
target.lib :: one.asm two.asm three.asm  
    ml one.asm two.asm three.asm  
    lib target one.obj two.obj three.obj  
target.lib :: four.c five.c  
    cl /c four.c five.c  
    lib target four.obj five.obj  
```  
  
## 참고 항목  
 [대상](../build/targets.md)