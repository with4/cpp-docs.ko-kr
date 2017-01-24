---
title: "다중 스레드 응용 프로그램이 서로 다른 여러 스레드에서 MFC DLL에 액세스할 수 있습니까? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], 다중 스레딩"
  - "MFC DLL[C++], 다중 스레딩"
  - "다중 스레딩[C++], DLL"
  - "스레딩[MFC], DLL"
ms.assetid: e3452e62-021e-4d23-9cce-cff41eb8b46b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 다중 스레드 응용 프로그램이 서로 다른 여러 스레드에서 MFC DLL에 액세스할 수 있습니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다중 스레드 응용 프로그램은 서로 다른 스레드에서 동적으로 MFC 및 확장 DLL에 링크하는 기본 DLL에 액세스할 수 있습니다.  또한 Visual C\+\+ 버전 4.2부터 응용 프로그램에서는 해당 응용 프로그램에서 만들어진 여러 스레드에서 정적으로 MFC에 링크하는 기본 DLL에 액세스할 수 있습니다.  
  
 버전 4.2 이전에는 하나의 외부 스레드만 정적으로 MFC에 링크하는 기본 DLL에 연결할 수 있었습니다.  여러 스레드에서 정적으로 MFC에 링크하는 기본 DLL에 액세스할 때의 제한 사항\(Visual C\+\+ 버전 4.2 이전\)에 대한 자세한 내용은 기술 자료 문서의 "Multiple Threads and MFC \_USRDLLs"\(Q122676\)을 참조하십시오.  
  
 USRDLL이라는 용어는 Visual C\+\+ 설명서에서 더 이상 사용되지 않습니다.  정적으로 MFC에 링크한 기본 DLL의 특징은 이전 USRDLL의 특징과 같습니다.  
  
## 참고 항목  
 [DLL 관련 질문과 대답](../build/dll-frequently-asked-questions.md)