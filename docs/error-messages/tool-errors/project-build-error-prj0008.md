---
title: "프로젝트 빌드 오류 PRJ0008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0008"
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 프로젝트 빌드 오류 PRJ0008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'file' 파일을 삭제할 수 없습니다.  
  
 **파일이 열려 있거나 쓰기 금지되어 있는지 확인하십시오.**  
  
 Visual C\+\+에서는 다시 빌드하거나 정리하는 중에 [일반 구성 설정 속성 페이지](../../ide/general-property-page-project.md)에 있는 **정리할 때 삭제할 확장명** 속성의 와일드카드 지정에 만족하는 파일뿐 아니라 빌드에 대한 알려진 중간 파일과 출력 파일을 모두 삭제합니다.  
  
 Visual C\+\+에서 파일을 삭제할 수 없는 경우 이 오류가 표시됩니다.  이 오류를 해결하려면 빌드를 수행하는 사용자를 위해 파일과 파일의 디렉터리를 쓰기 가능으로 설정합니다.