---
title: "NMAKE 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "명령 파일"
  - "명령 파일, NMAKE"
  - "NMAKE 프로그램, 실행"
  - "NMAKE 프로그램, 대상"
  - "지시 파일, NMAKE"
  - "대상"
  - "대상, 빌드"
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 실행
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## 설명  
 NMAKE는 지정된 *targets*만 빌드하고, 지정된 대상이 없는 경우 메이크파일의 첫 번째 대상을 빌드합니다.  다른 대상을 빌드하는 [의사 대상](../build/pseudotargets.md)이 첫 번째 메이크파일 대상이 될 수 있습니다.  NMAKE는 \/F로 지정된 메이크파일을 사용합니다. \/F가 지정되지 않은 경우에는 현재 디렉터리의 Makefile 파일을 사용합니다.  지정된 메이크파일이 없는 경우에는 유추 규칙을 사용하여 명령줄 *targets*를 빌드합니다.  
  
 `commandfile` 텍스트 파일\(또는 지시 파일\)에는 명령줄 입력이 포함되어 있습니다.  기타 입력은 @`commandfile` 앞 또는 뒤에 올 수 있습니다.  경로를 사용할 수 있습니다.  `commandfile`에서 줄 바꿈 문자는 공백으로 처리됩니다.  공백이 포함되어 있는 매크로 정의는 인용 부호로 묶습니다.  
  
## 추가 정보  
 [NMAKE 옵션](../build/nmake-options.md)  
  
 [Tools.ini와 NMAKE](../build/tools-ini-and-nmake.md)  
  
 [NMAKE의 종료 코드](../build/exit-codes-from-nmake.md)  
  
## 참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)