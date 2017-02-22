---
title: "BSCMAKE 오류 BK1513 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1513"
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# BSCMAKE 오류 BK1513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비증분 업데이트에는 모든 .SBR 파일이 필요합니다.  
  
 하나 이상의 .sbr 파일이 잘렸으므로 BSCMAKE에서 새 찾아보기 정보\(.bsc\) 파일을 빌드할 수 없습니다.  잘린 .sbr 파일의 이름을 찾으려면 이 오류와 함께 표시되는 [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) 경고를 확인하세요.  
  
 BSCMAKE는 잘린 .sbr 파일로 .bsc 파일을 업데이트할 수는 있지만 새 파일을 빌드할 수는 없습니다.  BSCMAKE는 다음과 같은 경우 새 .bsc 파일을 빌드할 수 있습니다.  
  
-   .bsc 파일이 없는 경우  
  
-   .bsc 파일에 잘못된 파일 이름을 지정한 경우  
  
-   .bsc 파일이 손상된 경우  
  
 이 문제를 해결하려면 잘린.sbr 파일을 삭제하고 다시 빌드하거나 솔루션을 정리하고 다시 빌드합니다.  이렇게 하려면 IDE에서 **빌드**, **솔루션 정리**를 차례로 선택한 다음 **빌드**, **솔루션 다시 빌드**를 차례로 선택합니다.