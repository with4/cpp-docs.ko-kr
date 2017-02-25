---
title: "리소스 컴파일러 심각한 오류 RC1120 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1120"
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 리소스 컴파일러 심각한 오류 RC1120
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메모리가 부족합니다. number 바이트가 필요합니다.  
  
 리소스 컴파일러가 힙에 저장할 항목에 대한 저장 공간이 부족합니다.  일반적으로 이 오류는 기호가 너무 많기 때문에 발생합니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  Windows 스왑 파일 공간을 늘이십시오.  스왑 파일 공간을 늘리는 방법에 대한 자세한 내용은 Windows 도움말의 가상 메모리 부분을 참조하십시오.  
  
2.  필요 없는 포함 파일 및 특히 `#define` 지시문과 함수 프로토타입을 제거하십시오.  
  
3.  현재 파일을 두 개 이상의 파일로 분리한 다음 개별적으로 컴파일하십시오.  
  
4.  다른 프로그램이나 드라이버가 실행 중이면 상당량의 메모리를 소비하므로 시스템에서 이들을 종료하십시오.