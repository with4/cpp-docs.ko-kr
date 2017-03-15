---
title: "NMAKE 심각한 오류 U1051 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1051"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1051"
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE 심각한 오류 U1051
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메모리가 부족합니다.  
  
 메이크파일이 너무 크거나 복잡하기 때문에 NMAKE에 가상 메모리를 포함하여 메모리가 부족합니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  디스크의 일부 공간을 비웁니다.  
  
2.  Windows NT의 페이징 파일이나 Windows의 스왑 파일 크기를 증가시킵니다.  
  
3.  메이크파일의 일부만 사용하는 경우 메이크파일을 개별 파일로 나누거나 **\!IF** 전처리 지시문을 사용하여 NMAKE의 처리량을 제한합니다.  **\!IF** 지시문에는 **\!IF**, `!IFDEF`, **\!IFNDEF**, **\!ELSE IF**, **\!ELSE** `IFDEF` 및 **\!ELSE** `IFNDEF`가 포함됩니다.