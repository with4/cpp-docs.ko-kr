---
title: "32비트 Windows 시간/날짜 서식 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.time"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "32비트 Windows"
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 32비트 Windows 시간/날짜 서식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파일 시간 및 날짜는 비트 필드로서 부호 없는 정수를 사용하여 개별적으로 저장됩니다.  파일의 날짜 및 시간을 압축하는 것은다음과 같습니다.  
  
### 시간  
  
|비트 위치:|0   1   2   3   4|Ctrl\+A|\[d, 4\] \[e, 5\] \[f, 6\]|  
|------------|-----------------------|-------------|--------------------------------|  
|길이:|5|6|5|  
|콘텐츠:|hours|minutes|2 초 증가|  
|값 범위:|0–23|0–59|2 초 간격으로 0–29|  
  
### 날짜  
  
|비트 위치:|0   1   2   3   4   5   6|Ctrl\+A|\[d, 4\] \[e, 5\] \[f, 6\]|  
|------------|-------------------------------|-------------|--------------------------------|  
|길이:|7|4|5|  
|콘텐츠:|년도|월|일|  
|값 범위:|0–119|1–12|1–31|  
||\(1980에 비례\)|||  
  
## 참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)