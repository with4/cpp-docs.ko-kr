---
title: "FreeLibrary 및 AfxFreeLibrary | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FreeLibrary"
  - "AfxFreeLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "확장 DLL[C++], 언로드"
  - "AfxFreeLibrary 메서드"
  - "DLL 언로드"
  - "FreeLibrary 메서드"
  - "DLL[C++], 연결"
  - "명시적 연결[C++]"
  - "DLL[C++], 언로드"
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# FreeLibrary 및 AfxFreeLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Processes that explicitly link to a DLL call the [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) function when the DLL module is no longer needed.  이 함수는 해당 모듈의 참조 횟수를 1만큼 줄이며, 참조 횟수가 0이면 프로세스의 주소 공간에서 해당 모듈을 매핑 해제합니다.  
  
 In an MFC application, use [AfxFreeLibrary](../Topic/AfxFreeLibrary.md) instead of `FreeLibrary` to unload an extension DLL.  `AfxFreeLibrary`용 인터페이스\(함수 프로토타입\)는 `FreeLibrary`의 경우와 같습니다.  
  
## 수행할 작업  
  
-   [암시적 링크](../build/linking-implicitly.md)  
  
-   [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)  
  
## 추가 정보  
  
-   [LoadLibrary 및 AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../Topic/AfxFreeLibrary.md)