---
title: "C 크기 조정 정수 형식 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "크기 조정 정수 형식"
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 크기 조정 정수 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 Microsoft C는 크기가 지정된 정수 형식을 지원합니다.  \_\_Int*n*을 사용하여 8비트, 16비트, 32비트 또는 64비트 정수 변수를 선언할 수 있습니다. 여기서 *n*은 정수 변수의 비트 크기입니다.  *n*의 값은 8, 16, 32 또는 64입니다.  다음 예제에서는 네 가지 형식의 크기가 지정된 정수 각각의 변수 하나를 선언합니다.  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 처음 세 가지 형식의 크기가 지정된 정수는 크기가 같은 ANSI 형식에 대한 동의어이며 여러 플랫폼에서 동일하게 동작하는 이식 가능한 코드 작성에 유용합니다.  \_\_int8 데이터 형식은 char 형식과 동의어이고, \_\_int16은 short 형식과 동의어이며, \_\_int32는 int 형식과 동의어입니다.  \_\_int64 형식에는 해당 ANSI 유형이 없습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [기본 형식의 저장소](../c-language/storage-of-basic-types.md)