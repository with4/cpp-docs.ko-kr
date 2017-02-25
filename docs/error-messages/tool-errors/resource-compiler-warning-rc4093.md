---
title: "리소스 컴파일러 경고 RC4093 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC4093"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4093"
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 리소스 컴파일러 경고 RC4093
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비활성 코드의 문자 상수에 이스케이프되지 않은 줄 바꿈 문자가 있습니다.  
  
 `#if`, `#elif`, **\#ifdef** 또는 **\#ifndef** 전처리기 지시문의 상수 식이 0으로 계산되어 뒤에 오는 코드가 비활성화되었습니다.  비활성 코드에 작은따옴표 또는 큰따옴표로 묶인 줄 바꿈 문자가 있습니다.  
  
 다음 큰따옴표가 나오기 전까지 모든 텍스트가 문자열 상수 안에 있는 것으로 간주됩니다.