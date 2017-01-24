---
title: "리소스 컴파일러 심각한 오류 RW1022 | Microsoft Docs"
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
  - "RW1022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW1022"
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 리소스 컴파일러 심각한 오류 RW1022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**파일에 쓰는 동안 I\/O 오류가 발생했습니다.**  
  
 리소스 컴파일러가 파일에 쓸 수 없습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  디스크 공간이 부족합니다.  사용 가능한 공간의 크기는 만들고 있는 실행 파일 크기의 두 배 이상이 되어야 합니다.  
  
2.  읽기 전용 볼륨입니다.  
  
3.  섹터가 잘못되었습니다.  
  
4.  공유 위반입니다.