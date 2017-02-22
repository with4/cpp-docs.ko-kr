---
title: "컴파일러 경고 (수준 1) C4650 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4650"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4650"
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4650
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 헤더에 디버깅 정보가 없습니다. 헤더의 전역 기호만 사용할 수 있습니다.  
  
 미리 컴파일된 헤더 파일이 Microsoft의 기호화된 디버깅 정보를 사용하여 컴파일되지 않았습니다.  
  
 따라서 링크될 때 결과로 만들어지는 실행 파일이나 동적 연결 라이브러리 파일에는 미리 컴파일된 헤더에 포함되어 있는 지역 기호에 대한 디버깅 정보가 포함되지 않습니다.  
  
 이 경고가 발생하지 않도록 하려면 미리 컴파일된 헤더 파일을 [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 명령줄 옵션을 사용하여 다시 컴파일하십시오.