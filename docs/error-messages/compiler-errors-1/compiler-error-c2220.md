---
title: "컴파일러 오류 C2220 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2220"
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2220
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

경고가 오류로 처리되어 생성된 개체 파일이 없습니다.  
  
 [\/WX](../../build/reference/compiler-option-warning-level.md)는 컴파일러가 모든 경고를 오류로 처리하도록 합니다.  오류가 발생했기 때문에, 개체나 실행 파일이 생성되지 않았습니다.  
  
 오류는 **\/WX** 플래그가 설정될 때에만 나타나고 경고는 컴파일하는 동안에 발생 합니다.  이 오류를 해결 하려면, 프로젝트의 모든 경고를 제거 해야 합니다.  
  
### 해결하려면, 다음 방법 중 하나를 사용합니다  
  
-   프로젝트에서 경고를 발생 시키는 문제를 해결 합니다.  
  
-   낮은 경고 수준에서 컴파일합니다 — 예를 들어 **\/W3** 를 사용합니다 \(**\/W4**대신\).  
  
-   [경고](../../preprocessor/warning.md) pragma를 사용하여 사용 안 함 또는 특정 경고를 표시 합니다.  
  
-   컴파일 하기 위해 **\/WX** 사용하지 않습니다.