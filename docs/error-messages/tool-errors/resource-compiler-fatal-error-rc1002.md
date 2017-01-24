---
title: "리소스 컴파일러 심각한 오류 RC1002 | Microsoft Docs"
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
  - "RC1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1002"
ms.assetid: b43dfece-0dc3-4d0b-9d8f-509699b9ae80
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 리소스 컴파일러 심각한 오류 RC1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙 공간이 부족합니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  Windows 스왑 파일 공간을 늘입니다.  스왑 파일 공간을 늘리는 방법에 대한 자세한 내용은 Windows 도움말의 가상 메모리 부분을 참조하십시오.  
  
2.  현재 파일을 더 작은 파일로 분할하여 별도로 컴파일하십시오.  
  
3.  시스템에서 실행하고 있는 다른 드라이버나 프로그램을 제거합니다.