---
title: "NMAKE 심각한 오류 U1035 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1035"
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE 심각한 오류 U1035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류: ':' 또는 '\=' 구분 기호가 있어야 합니다.  
  
 콜론\(**:**\) 또는 등호\(**\=**\)가 있어야 합니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  대상 뒤에 콜론이 없습니다.  
  
2.  콜론이 공백 문자 없이 단일 문자 대상 뒤에 있습니다.  NMAKE는 이를 드라이브 지정으로 해석합니다.  
  
3.  콜론이 유추 규칙을 따르지 않았습니다.  
  
4.  매크로 정의 뒤에 등호가 없습니다.  
  
5.  명령을 새 줄로 계속하는데 사용하는 백슬래시\(**\\**\) 뒤에 문자가 있습니다.  
  
6.  NMAKE 구문 규칙을 따르지 않는 문자열이 표시되었습니다.  
  
7.  메이크파일의 서식이 워드 프로세서에서 지정되었습니다.