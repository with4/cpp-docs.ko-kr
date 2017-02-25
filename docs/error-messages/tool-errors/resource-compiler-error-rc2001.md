---
title: "리소스 컴파일러 오류 RC2001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2001"
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 리소스 컴파일러 오류 RC2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상수에 줄 바꿈 문자가 있습니다.  
  
 백슬래시\(**\\**\) 또는 닫는 큰따옴표\(**"**\) 및 여는 큰따옴표\(**"**\)가 없이 문자열 상수가 둘째 줄로 계속되었습니다.  
  
 소스 파일에서 두 줄에 걸쳐 있는 문자열 상수를 나누려면 다음 중 하나를 수행합니다.  
  
-   줄 연속 문자인 백슬래시를 첫째 줄 끝에 붙입니다.  
  
-   첫째 줄에서 큰따옴표로 문자열을 닫고 다음 줄에서 다른 큰따옴표로 문자열을 엽니다.  
  
 문자열 상수에 줄 바꿈 문자를 포함하는 데 사용하는 이스케이프 시퀀스인 \\n으로 첫 줄을 끝내는 것으로는 충분하지 않습니다.