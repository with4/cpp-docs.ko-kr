---
title: "파일 위치 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "파일 포인터[C++], 파일 위치 오류"
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 파일 위치 오류
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.9.9.1, 4.9.9.4** 실패 시 `errno` 매크로가 `fgetpos` 또는 `ftell` 함수를 통해 설정되는 값  
  
 `fgetpos` 또는 `ftell`이 실패할 때 `errno`는 위치가 유효하지 않은 경우 매니페스트 상수 `EINVAL`로 설정되고 파일 번호가 잘못된 경우 EBADF로 설정됩니다.  상수는 ERRNO.H에서 정의됩니다.  
  
## 참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)