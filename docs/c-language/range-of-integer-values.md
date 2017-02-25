---
title: "정수 값 범위 | Microsoft Docs"
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
ms.assetid: 0e9c6161-8f3f-4bfb-9fcc-a6c8dc97d702
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 정수 값 범위
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.1.2.5** 다양한 형식의 정수 값에 대한 표현 및 집합  
  
 정수는 32비트\(4바이트\)를 포함합니다.  부호 있는 정수는 2의 보수 형식으로 표시됩니다.  최상위 비트는 음수에 대해서는 부호 1을, 양수와 0에 대해서는 0을 가집니다.  값은 아래와 같습니다.  
  
|형식|최소값 및 최대값|  
|--------|---------------|  
|**unsigned short**|0~65535|  
|`signed short`|–32768~32767|  
|`unsigned long`|0 ~ 4294967295|  
|**signed long**|–2147483648~2147483647|  
  
## 참고 항목  
 [정수](../c-language/integers.md)