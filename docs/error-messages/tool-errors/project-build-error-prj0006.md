---
title: "프로젝트 빌드 오류 PRJ0006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0006"
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 프로젝트 빌드 오류 PRJ0006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'file' 임시 파일을 열 수 없습니다.파일이 없거나 디렉터리가 쓰기 금지되어 있는지 확인하십시오.  
  
 Visual C\+\+에서 빌드 프로세스 중에 임시 파일을 만들 수 없습니다.  그 이유는 다음과 같습니다.  
  
-   임시 디렉터리가 없습니다.  
  
-   읽기 전용 임시 디렉터리입니다.  
  
-   디스크 공간이 부족합니다.  
  
-   $\(IntDir\) 폴더가 읽기 전용이거나 읽기 전용 임시 파일이 들어 있습니다.  
  
 이 오류는 오류 PRJ0007, "'directory' 출력 디렉터리를 만들 수 없습니다."에 뒤이어 발생하기도 합니다.  오류 PRJ0007은 $\(IntDir\) 디렉터리를 만들 수 없음을 뜻하며 이 경우 임시 파일도 만들 수 없습니다.  
  
 다음을 지정할 때마다 임시 파일이 만들어집니다.  
  
-   지시 파일  
  
-   사용자 지정 빌드 단계  
  
-   빌드 이벤트