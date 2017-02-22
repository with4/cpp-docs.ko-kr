---
title: "DLL의 자동화 | Microsoft Docs"
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
  - "자동화[C++], DLL"
  - "DLL[C++], 자동화"
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# DLL의 자동화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC DLL 마법사에서 자동화 옵션을 선택하면 마법사에서 다음과 같은 항목을 제공합니다.  
  
-   기초 개체 설명 언어 파일\(.ODL\)  
  
-   Afxole.h에 대한 STDAFX.h 파일의 include 지시문  
  
-   **AfxDllGetClassObject** 함수를 호출하는 `DllGetClassObject` 함수 구현  
  
-   **AfxDllCanUnloadNow** 함수를 호출하는 `DllCanUnloadNow` 함수 구현  
  
-   [COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md) 함수를 호출하는 `DllRegisterServer` 함수 구현  
  
## 추가 정보  
  
-   [자동화 서버](../mfc/automation-servers.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)