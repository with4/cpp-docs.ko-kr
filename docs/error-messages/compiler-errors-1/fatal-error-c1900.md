---
title: "심각한 오류 C1900 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1900"
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 심각한 오류 C1900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'tool1' 버전 'number1'과\(와\) 'tool2' 버전 'number2' 사이에 II이 일치하지 않습니다.  
  
 컴파일러의 여러 패스에서 실행되는 도구가 일치하지 않습니다.  ***number1*** 및 ***number2***는 파일의 날짜를 참조합니다.  예를 들어 패스 1에서는 컴파일러 프런트 엔드가 실행되고\(c1.dll\) 패스 2에서는 컴파일러 백 엔드가 실행됩니다\(c2.dll\)  파일의 날짜는 일치해야 합니다.  
  
 이 문제를 해결하려면 Visual Studio에 모든 업데이트가 적용되었는지 확인합니다.  문제가 계속 발생하면 Windows 제어판에서 **프로그램 및 기능**을 사용하여 Visual Studio를 복구하거나 다시 설치합니다.