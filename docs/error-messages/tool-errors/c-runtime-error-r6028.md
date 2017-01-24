---
title: "C 런타임 오류 R6028 | Microsoft Docs"
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
  - "R6028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6028"
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
caps.latest.revision: 9
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C 런타임 오류 R6028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙을 초기화할 수 없습니다.  
  
 이 오류는 운영 체제에서 응용 프로그램의 메모리 풀을 만드는 데 실패한 경우에 발생합니다.  특히 Win32 함수 `HeapCreate`를 호출한 C 런타임\(CRT\)이 NULL을 반환하면 작업에 실패했음을 의미합니다.  
  
 응용 프로그램을 시작하는 동안 이 오류가 발생하면 결함이 있는 드라이브가 로드되기 때문에 시스템이 힙 요청을 만족시킬 수 없습니다.  Windows 업데이트 또는 하드웨어 공급업체 웹 사이트에서 업데이트된 드라이버를 확인하십시오.