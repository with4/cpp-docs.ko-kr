---
title: "컴파일러 오류 C2212 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2212"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2212"
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2212
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': \_\_based는 함수에 대한 포인터에 사용할 수 없습니다.  
  
 함수에 대한 포인터를 `__based`로 선언할 수 없습니다.  코드 기반 데이터가 필요한 경우에는 `__declspec` 키워드나 `data_seg` pragma를 사용하십시오.