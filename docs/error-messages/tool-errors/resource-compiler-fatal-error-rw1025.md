---
title: "리소스 컴파일러 심각한 오류 RW1025 | Microsoft Docs"
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
  - "RW1025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW1025"
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 리소스 컴파일러 심각한 오류 RW1025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

far 힙 메모리가 부족합니다.  
  
 너무 많은 공간을 차지하는 메모리 상주 소프트웨어가 있는지 확인하십시오.  또한 CHKDSK 프로그램을 사용하여 보유하고 있는 메모리 양을 확인하십시오.  
  
 큰 리소스 파일을 만드는 경우 리소스 스크립트를 두 개의 파일로 분할합니다.  두 개의 .res 파일을 만든 후 다음과 같이 MS\-DOS 명령줄을 사용하여 두 파일을 조인하십시오.  
  
```  
copy first.res /b + second.res /b full.res  
```