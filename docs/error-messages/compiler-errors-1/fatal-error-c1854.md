---
title: "심각한 오류 C1854 | Microsoft Docs"
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
  - "C1854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1854"
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 헤더를 개체 파일 'filename'에 만드는 동안 구성된 정보를 덮어쓸 수 없습니다.  
  
 동일한 파일에 **\/Yc**\(미리 컴파일된 헤더 생성\) 옵션을 지정한 후에 **\/Yu**\(미리 컴파일된 헤더 사용\) 옵션을 지정했습니다.  `__declspec` `dllexport`를 포함하는 선언 등의 일부 선언에서는 이렇게 지정할 수 없습니다.