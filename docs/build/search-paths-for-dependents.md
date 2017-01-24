---
title: "종속 파일의 경로 검색 | Microsoft Docs"
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
  - "종속 파일, NMAKE"
  - "NMAKE 프로그램, 종속 파일"
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 종속 파일의 경로 검색
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 종속 파일에는 아래에 지정된 것과 같이 선택적 검색 경로가 있습니다.  
  
## 구문  
  
```  
{directory[;directory...]}dependent  
```  
  
## 설명  
 NMAKE는 먼저 현재 디렉터리에서 종속 파일을 찾은 다음 지정된 순서로 다른 디렉터리에서 찾습니다.  매크로를 사용하여 전부 또는 일부 검색 경로를 지정할 수 있습니다.  디렉터리 이름은 중괄호\({ }\)로 묶고 디렉터리가 여러 개인 경우 세미콜론\(;\)으로 구분합니다.  공백이나 탭은 사용할 수 없습니다.  
  
## 참고 항목  
 [종속 파일](../build/dependents.md)