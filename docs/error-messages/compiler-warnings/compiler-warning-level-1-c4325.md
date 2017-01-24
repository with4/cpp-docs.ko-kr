---
title: "컴파일러 경고 (수준 1) C4325 | Microsoft Docs"
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
  - "C4325"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4325"
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4325
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***section* ' 표준 섹션의 특성이 무시됩니다.**  
  
 표준 섹션의 특성을 변경하면 안 됩니다.  예를 들면 다음과 같습니다.  
  
```  
#pragma section(".sdata", long)  
```  
  
 이 코드는 **short** 데이터 형식을 사용하는 `.sdata` 표준 섹션을 **long** 데이터 형식으로 덮어쓰게 됩니다.  
  
 특성을 변경하면 안 되는 표준 섹션은 다음과 같습니다.  
  
-   .data  
  
-   .sdata  
  
-   .bss  
  
-   .sbss  
  
-   .text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 다른 섹션은 추후에 추가됩니다.  
  
## 참고 항목  
 [섹션](../../preprocessor/section.md)