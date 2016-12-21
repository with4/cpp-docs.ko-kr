---
title: "링커 도구 오류 LNK1000 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1000"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1000"
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1000
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

알 수 없는 오류입니다. 기술 지원 옵션을 보려면 설명서를 참조하십시오.  
  
 오류가 발생한 상황을 기록하고 문제점을 파악하여 재현할 수 있는 테스트 사례를 만듭니다. `Microsoft Product Support Services`를 참조하십시오.  자세한 내용은 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650)을 참조하십시오.  
  
 표준 헤더 파일\(dos.h 등\)과 자체 파일이 뒤섞인 경우 이 오류가 발생할 수 있습니다.  `#include`를 사용하여 표준 헤더 파일을 먼저 포함한 다음 자체 헤더 파일을 포함하십시오.