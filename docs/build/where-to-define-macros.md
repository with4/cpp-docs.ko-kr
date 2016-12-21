---
title: "매크로를 정의할 위치 | Microsoft Docs"
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
  - "매크로 정의"
  - "매크로, NMAKE"
  - "NMAKE 프로그램, 매크로 정의"
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 매크로를 정의할 위치
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

매크로는 명령줄, 명령 파일, 메이크파일 또는 Tools.ini 파일에 정의합니다.  
  
 메이크파일이나 Tools.ini 파일에서 각 매크로 정의는 별도의 줄에 표시되어야 하며 공백이나 탭으로 시작할 수 없습니다.  등호 앞뒤의 공백이나 탭은 무시됩니다.  매크로 앞뒤의 인용 부호와 문자열에 포함된 공백을 비롯한 모든 [문자열](../build/defining-an-nmake-macro.md)은 리터럴 문자입니다.  
  
 명령줄이나 명령 파일에서 공백과 탭은 인수를 구분하며 등호 앞뒤에 올 수 없습니다.  `string` 안에 공백이나 탭이 포함된 경우 문자열 자체 또는 전체 매크로를 큰따옴표\(" "\)로 묶습니다.  
  
## 참고 항목  
 [NMake 매크로 정의](../build/defining-an-nmake-macro.md)