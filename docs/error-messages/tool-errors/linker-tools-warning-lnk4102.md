---
title: "링커 도구 경고 LNK4102 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4102"
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 경고 LNK4102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

삭제 중인 'name' 소멸자를 내보냅니다. 이미지가 올바르게 실행되지 않을 수도 있습니다.  
  
 삭제 중인 소멸자를 프로그램이 내보내려고 했습니다.  이로 인해 삭제가 DLL 경계를 넘어서서 발생하므로 프로세스가 점유되지 않은 메모리를 확보할 수 있습니다.  지정된 기호가 .def 파일에 표시되지 않도록 하고 이 기호가 링커 명령줄에서 **\/IMPORT** 또는 **\/EXPORT** 옵션의 인수로 표시되지 않도록 하십시오.  
  
 C 런타임 라이브러리를 다시 빌드하는 중이면 이 메시지를 무시해도 됩니다.