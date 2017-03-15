---
title: "최대 문자열 길이 | Microsoft Docs"
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
  - "길이, 문자열"
  - "최대 문자열 길이"
  - "문자열 길이, 최대"
  - "문자열[C++], 길이"
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 최대 문자열 길이
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 ANSI 호환성을 위해 컴파일러가 연결 후 문자열 리터럴에 최대 509개 문자를 허용해야 합니다.  Microsoft C에서 허용하는 문자열 리터럴의 최대 길이는 약 2,048바이트입니다.  그러나 문자열 리터럴이 큰따옴표로 묶인 여러 부분으로 이루어진 경우 전처리기가 이러한 부분을 단일 문자열로 연결하고 연결된 줄마다 총 바이트 수에 바이트를 더 추가합니다.  
  
 예를 들어, 각 줄에 50자가 있는 40줄\(2,000자\), 7자가 있는 1줄로 구성되고 각 줄이 큰따옴표로 묶인 문자열이 있습니다.  2,007바이트에 null 문자를 종결하는 1바이트를 더하여 총 2,008바이트가 됩니다.  연결할 때 처음 40줄에 대해 각각 문자가 더 추가됩니다.  그러면 총 2,048바이트가 됩니다.  그러나 큰따옴표 대신 줄 연속\(\\\)이 사용되면 전처리기가 각 줄에 대해 문자를 더 추가하지 않습니다.  
  
 따옴표가 붙은 개별 문자열은 2048바이트 이하여야 하며 문자열을 연결하여 약 65535바이트의 문자열 리터럴을 생성할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [C 문자열 리터럴](../c-language/c-string-literals.md)