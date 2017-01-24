---
title: "리소스 컴파일러 오류 RC2148 | Microsoft Docs"
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
  - "RC2148"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2148"
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 리소스 컴파일러 오류 RC2148
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

SUBLANGUAGE ID가 너무 큽니다.  
  
 SUBLANGUAGE ID 값이 범위를 벗어났습니다.  
  
 **LANGUAGE** 문에는 다음 구문을 사용해야 합니다.  
  
 **LANGUAGE** *primary\_language\_ID*,*secondary\_language\_ID*  
  
 유효한 SUBLANGUAGE ID는 WINNT.h 파일에 **SUBLANG\_** 상수로 정의되어 있습니다.