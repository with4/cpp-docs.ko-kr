---
title: "CVTRES 심각한 오류 CVT1100 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CVT1100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVT1100"
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# CVTRES 심각한 오류 CVT1100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리소스가 중복되었습니다. 형식::type, 이름:name, 언어:language, 플래그:flags, 크기:size  
  
 리소스가 두 번 이상 지정되었습니다.  
  
 링커가 형식 라이브러리를 만들고 있으며 사용자가 [\/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md)를 지정하지 않은 경우에 프로젝트의 리소스가 이미 1을 사용하고 있으면 이 오류가 발생합니다.  이런 경우 \/TLBID를 지정한 다음 65535까지의 다른 숫자를 지정합니다.