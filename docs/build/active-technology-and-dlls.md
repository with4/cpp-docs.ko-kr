---
title: "액티브 기술 및 DLL | Microsoft Docs"
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
  - "액티브 기술[C++]"
  - "자동화[C++], DLL"
  - "DLL[C++], 액티드 기술"
  - "in-process 서버 DLL"
  - "MFC DLL[C++], 액티드 기술"
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 액티브 기술 및 DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

액티브 기술은 DLL 내에서 개체 서버가 완전히 구현되도록 합니다.  이러한 형식의 서버를 in\-process 서버라고 합니다.  MFC는 모든 비주얼 편집 기능에 대해 in\-process 서버를 완전히 지원하지는 않습니다. 그 이유는 서버가 컨테이너의 기본 메시지 루프 안으로 후크될 수 있는 방법이 액티브 기술에 없기 때문입니다.  MFC에서 액셀러레이터 키 및 유휴 시간 프로세스를 처리하기 위해서는 컨테이너 응용 프로그램의 메시지 루프에 액세스해야 합니다.  
  
 사용자 인터페이스가 없는 자동화 서버를 작성하는 경우에는 해당 서버를 in\-process 서버로 만든 다음 DLL에 완전히 포함시킬 수 있습니다.  
  
## 추가 정보  
  
-   [자동화 서버](../mfc/automation-servers.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)