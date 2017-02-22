---
title: "링커 도구 경고 LNK4206 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4206"
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 경고 LNK4206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 형식 정보를 찾을 수 없습니다. 'filename'이\(가\) 링크되지 않았거나 덮어쓰여졌습니다. 디버그 정보가 없는 것처럼 개체를 링크합니다.  
  
 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md)로 컴파일한 지정된 개체 파일이 LINK 명령에 지정되지 않았거나 덮어쓰여졌습니다.  
  
 이 경고가 발생하는 일반적인 시나리오로는 \/Yc를 사용하여 컴파일한 .obj가 라이브러리에 있지만 이 .obj에 대한 기호 참조가 코드에 없는 경우를 들 수 있습니다.  이 경우 링커는 .obj 파일을 사용하거나 확인하지 않습니다.  이러한 상황에서는 코드를 다시 컴파일하고 나머지 개체\(\/Yc를 사용하여 컴파일하지 않은 개체\)에 대해 [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)을 사용해야 합니다.