---
title: "컴파일러 경고 (수준 1) C4049 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4049"
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 줄 번호 내보내기를 종료하고 있습니다.  
  
 파일에 16,777,215\(2<sup>24</sup>\-1\)가 넘는 소스 줄이 들어 있습니다.  컴파일러는 16,777,215에서 번호 매기기를 중지합니다.  
  
 16,777,215번째 줄 이후의 코드에 대해 다음과 같은 문제가 발생할 수 있습니다.  
  
-   줄 번호에 대한 디버그 정보가 이미지에 포함되지 않습니다.  
  
-   일부 진단을 보고할 때 잘못된 줄 번호가 사용됩니다.  
  
-   .asm 목록\(\/FAs\)의 줄 번호가 잘못될 수 있습니다.