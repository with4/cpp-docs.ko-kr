---
title: "리소스 컴파일러 오류 RC2151 | Microsoft Docs"
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
  - "RC2151"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2151"
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 리소스 컴파일러 오류 RC2151
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열 상수를 다시 사용할 수 없습니다.  
  
 **STRINGTABLE** 문에서 같은 값을 두 번 사용했습니다.  중복되는 10진수 값과 16진수 값을 함께 사용하지 않아야 합니다.  
  
 **STRINGTABLE**의 각 ID는 고유해야 합니다.  최고의 효율성을 위해 16의 배수로 시작하는 연속적인 상수를 사용하십시오.