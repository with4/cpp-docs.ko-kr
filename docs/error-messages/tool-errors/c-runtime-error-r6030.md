---
title: "C 런타임 오류 R6030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6030"
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# C 런타임 오류 R6030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT가 초기화되지 않았습니다.  
  
 이 오류는 CRT를 사용하고 있지만 CRT 시작 코드가 실행되지 않은 경우에 발생합니다.  링커 스위치 [\/ENTRY](../../build/reference/entry-entry-point-symbol.md)를 사용하여 기본 시작 주소를 재정의한 경우에 이 오류가 발생할 수 있습니다. 기본 시작 주소는 일반적으로 콘솔 EXE의 경우 **mainCRTStartup**, **wmainCRTStartup**이고, Windows EXE의 경우 **WinMainCRTStartup** 또는 **wWinMainCRTStartup**이고, DLL의 경우 **\_DllMainCRTStartup**입니다.  시작 시 위 함수 중 하나를 호출하지 않으면 C 런타임이 초기화되지 않습니다.