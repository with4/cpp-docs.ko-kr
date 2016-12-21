---
title: "심각한 오류 C1067 | Microsoft Docs"
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
  - "C1067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1067"
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 형식 레코드 크기의 64K 한도를 초과했습니다.  
  
 이 오류는 기호의 데코레이팅된 이름이 247자를 초과하는 경우에 발생할 수 있습니다.  이 오류를 해결하려면 기호 이름의 길이를 줄여야 합니다.  
  
 컴파일러에서 디버그 정보를 생성할 때는 소스 코드에서 발견한 형식을 정의하기 위한 형식 레코드가 작성됩니다.  예를 들어, 형식 레코드에 함수의 간단한 구조체와 인수 목록이 포함될 수 있습니다.  이러한 형식 레코드 중 일부는 목록의 크기가 클 수 있습니다.  
  
 모든 형식 레코드의 크기는 64K로 제한되어 있습니다.  이 64K 한도를 초과하면 이 오류가 발생합니다.  
  
 C1067은 이름이 긴 기호가 많거나 클래스, 구조체 또는 공용 구조체에 멤버가 너무 많은 경우에도 발생할 수 있습니다.