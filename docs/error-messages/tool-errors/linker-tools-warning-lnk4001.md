---
title: "링커 도구 경고 LNK4001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4001"
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 경고 LNK4001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체 파일이 지정되지 않았습니다. 라이브러리가 사용됩니다.  
  
 링커에 하나 이상의 .lib 파일이 전달되었지만 .obj 파일은 전달되지 않았습니다.  
  
 링커는 .lib 파일의 정보에 액세스할 수 없고 .obj 파일의 정보에 액세스할 수 있으므로 이 경고는 다른 링커 옵션을 명시적으로 지정해야 함을 나타냅니다.  예를 들어, [\/MACHINE](../../build/reference/machine-specify-target-platform.md), [\/OUT](../../build/reference/out-output-file-name.md) 또는 [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) 옵션을 지정해야 합니다.