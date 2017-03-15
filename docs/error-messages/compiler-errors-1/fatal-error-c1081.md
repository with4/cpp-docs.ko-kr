---
title: "심각한 오류 C1081 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1081"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1081"
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 심각한 오류 C1081
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 파일 이름이 너무 깁니다.  
  
 파일 경로 이름의 길이가 `_MAX_PATH`\(STDLIB.h에 의해 260자로 정의됨\)를 초과합니다.  파일 이름을 줄이십시오.  
  
 짧은 파일 이름을 가진 CL.exe를 호출하면 컴파일러가 전체 경로 이름을 생성해야 할 수도 있습니다.  예를 들어, `cl -c myfile.cpp`는 컴파일러가 다음을 생성하도록 합니다.  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```