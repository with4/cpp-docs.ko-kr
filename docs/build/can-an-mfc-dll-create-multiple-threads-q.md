---
title: "MFC DLL은 여러 스레드를 만들 수 있습니까? | Microsoft Docs"
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
ms.assetid: 41d5b5e6-a7d3-42bf-b641-f1245abd1c59
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MFC DLL은 여러 스레드를 만들 수 있습니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC DLL이 초기화 중일 때에만 제외하면 **TlsAlloc** 같은 Win32 TLS\(스레드 로컬 저장소\) 함수를 사용하여 스레드 로컬 저장소를 할당하는 한 여러 개의 스레드를 안전하게 만들 수 있습니다.  그러나 MFC DLL이 **\_\_declspec\(thread\)**를 사용하여 스레드 로컬 저장소를 할당하는 경우, 클라이언트 응용 프로그램은 DLL에 암시적으로 링크되어야 합니다.  클라이언트 응용 프로그램이 DLL에 명시적으로 링크하는 경우에는 **LoadLibrary** 호출로 DLL을 올바르게 로드할 수 없습니다.  MFC DLL 내에서 여러 스레드를 만드는 방법에 대한 자세한 내용은 기술 자료 문서, "PRB: Calling LoadLibrary\(\) to Load a DLL That Has Static TLS"\(Q118816\)를 참조하십시오.  
  
 시작하는 동안 새 MFC 스레드를 만드는 MFC DLL은 응용 프로그램에서 로드될 때 응답을 중지합니다.  여기에는 다음과 같은 항목 내에서 `AfxBeginThread` 또는 `CWinThread::CreateThread` 호출로 스레드가 만들어지는 때에도 포함됩니다.  
  
-   기본 DLL에 있는 `CWinApp` 파생 개체의 `InitInstance`  
  
-   기본 DLL에 제공되는 `DllMain` 또는 **RawDllMain** 함수  
  
-   확장 DLL에 제공되는 `DllMain` 또는 **RawDllMain** 함수  
  
 초기화 시 스레드를 만드는 것에 대한 자세한 내용은 기술 자료 문서의 "PRB: Cannot Create an MFC Thread During DLL Startup"\(Q142243\)를 참조하십시오.  
  
## 참고 항목  
 [DLL 관련 질문과 대답](../build/dll-frequently-asked-questions.md)