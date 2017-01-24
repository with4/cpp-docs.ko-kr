---
title: "명령줄 경고 D9026 | Microsoft Docs"
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
  - "D9026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9026"
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 명령줄 경고 D9026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전체 명령줄에 옵션이 적용됩니다.  
  
 파일 이름을 지정한 다음 명령에 옵션이 지정되었습니다.  옵션은 선행하는 파일에 적용되었습니다.  
  
 예를 들면 다음과 같습니다.  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 이 명령에서 VERDI.c 파일은 기본값인 \/G4 대신에 \/G5 옵션을 사용하여 컴파일됩니다.  
  
 이 동작은 이전 버전의 일부 동작과 다릅니다. 이전 버전에서는 파일 이름 앞에 지정한 옵션만 적용되므로 VERDI.c는 \/G4 옵션을 사용하여 컴파일되고 PUCCINI.c는 \/G5를 사용하여 컴파일되었습니다.