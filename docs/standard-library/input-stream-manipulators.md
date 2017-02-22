---
title: "입력 스트림 조작자 | Microsoft Docs"
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
  - "입력 스트림 개체"
  - "입력 스트림, 조작자"
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 입력 스트림 조작자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Many manipulators, such as [setprecision](../Topic/setprecision.md), are defined for the `ios` class and thus apply to input streams.  Few manipulators, however, actually affect input stream objects.  Of those that do, the most important are the radix manipulators, `dec`, `oct`, and `hex`, which determine the conversion base used with numbers from the input stream.  
  
 On extraction, the `hex` manipulator enables processing of various input formats.  For example, c, C, 0xc, 0xC, 0Xc, and 0XC are all interpreted as the decimal integer 12.  Any character other than 0 through 9, A through F, a through f, x, and X terminates the numeric conversion.  Thus the sequence `"124n5"` is converted to the number 124 with the [basic\_ios::fail](../Topic/basic_ios::fail.md) bit set.  
  
## 참고 항목  
 [Input Streams](../standard-library/input-streams.md)