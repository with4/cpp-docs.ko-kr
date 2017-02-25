---
title: "심각한 오류 C1902 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1902"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1902"
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 심각한 오류 C1902
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램 데이터베이스 관리자가 일치하지 않습니다. 설치를 확인하십시오.  
  
 컴파일러가 시스템에서 찾은 버전보다 최신 버전의 mspdb*XX*.dll을 사용하여 프로그램 데이터베이스 파일\(.pdb\)을 만들었습니다.  이 오류는 일반적으로 mspdbsrv.exe 또는 mspdbcore.dll이 없거나 mspdb*XX*.dll과 버전이 다름을 나타냅니다. *XX* 파일 이름의*XX* 자리 표시자는 각 제품 릴리스에 따라 달라집니다.  예를 들어 [!INCLUDE[vsprvslong](../../error-messages/compiler-errors-1/includes/vsprvslong_md.md)]에서는 이 파일 이름이 mspdb80.dll입니다.  
  
 시스템에 서로 버전이 일치하는 mspdbsrv.exe, mspdbcore.dll 및 mspdb*XX*.dll이 설치되어 있는지 확인하십시오.  일치하지 않는 버전이 대상 플랫폼의 컴파일러 및 링크 도구가 들어 있는 디렉터리에 복사되지 않았는지 확인하십시오.  예를 들어 **PATH** 환경 변수를 적절하게 설정하지 않고도 명령 프롬프트에서 컴파일러 또는 링크 도구를 호출할 수 있도록 파일을 복사했을 수 있습니다.