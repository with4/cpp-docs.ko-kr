---
title: "식 계산기 오류 CXX0030 | Microsoft Docs"
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
  - "CXX0030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0030"
  - "CXX0030"
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 식 계산기 오류 CXX0030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

식을 계산할 수 없습니다.  
  
 디버거의 식 계산기가 작성된 식에 대한 값을 얻을 수 없습니다.  식이 프로그램의 주소 공간 범위 밖에 있는 메모리를 참조하기 때문일 수도 있습니다\(예: null 포인터를 역참조함\).  Windows를 사용하면 프로그램의 주소 공간 범위 밖에 있는 메모리에 액세스할 수 없습니다.  
  
 괄호를 사용하여 식을 다시 작성하면 계산의 순서를 제어할 수 있습니다.  
  
 이 오류는 CAN0030과 동일합니다.