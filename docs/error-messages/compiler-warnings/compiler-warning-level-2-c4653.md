---
title: "컴파일러 경고 (수준 2) C4653 | Microsoft Docs"
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
  - "C4653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4653"
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'option' 컴파일러 옵션이 미리 컴파일된 헤더와 일치하지 않습니다. 현재 명령줄 옵션이 무시됩니다.  
  
 [\/Yu](../../build/reference/yu-use-precompiled-header-file.md)\(미리 컴파일된 헤더 사용\) 옵션을 통해 지정한 옵션이 미리 컴파일된 헤더를 만들 때 지정한 옵션과 다릅니다.  현재 컴파일에서는 미리 컴파일된 헤더를 만들 때 지정한 옵션을 사용했습니다.  
  
 미리 컴파일된 헤더를 컴파일하는 동안 [\/Zp](../../build/reference/zp-struct-member-alignment.md)\(팩 구조\) 옵션에 대한 값을 다르게 지정했을 때 이 경고가 발생합니다.