---
title: "리소스 컴파일러 오류 RC4005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4005"
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 리소스 컴파일러 오류 RC4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 매크로 재정의  
  
 식별자가 두 번 정의되었습니다.  컴파일러는 두 번째 매크로 정의를 사용했습니다.  
  
 명령줄에 매크로를 정의하고 코드 안에 `#define` 지시문으로 동일한 매크로를 정의하는 경우에 이 경고가 발생합니다.  또한 이 경고는 포함 파일에서 가져온 매크로 때문에 발생할 수 있습니다.  
  
 이 경고를 제거하려면 정의 중 하나를 제거하거나 두 번째 정의 전에 `#undef` 지시문을 사용합니다.