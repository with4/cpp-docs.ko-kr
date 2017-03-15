---
title: "NMAKE의 종료 코드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "종료 코드"
  - "NMAKE 프로그램, 종료 코드"
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# NMAKE의 종료 코드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE가 반환하는 종료 코드는 다음과 같습니다.  
  
|코드|의미|  
|--------|--------|  
|0|오류 없음\(경고일 수 있음\)|  
|1|불완전한 빌드\(\/K를 사용한 경우에만 발생\)|  
|2|프로그램 오류를 의미하며 가능한 발생 원인은 다음 중 하나입니다.|  
||-   메이크파일의 구문 오류|  
||-   오류 또는 명령의 종료 코드|  
||-   사용자의 중단|  
|4|메모리 부족으로 인한 시스템 오류|  
|255|대상이 최신 상태가 아님\(\/Q를 사용한 경우에만 발생\)|  
  
## 참고 항목  
 [NMAKE 실행](../build/running-nmake.md)