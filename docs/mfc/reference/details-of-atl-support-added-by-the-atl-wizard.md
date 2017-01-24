---
title: "ATL 마법사로 추가한 ATL 지원에 대한 세부 정보 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.atl.support"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, MFC 프로젝트"
  - "MFC, ATL 지원"
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 마법사로 추가한 ATL 지원에 대한 세부 정보
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[기존 MFC 실행 파일이나 DLL에 ATL 지원을 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)할 경우 Visual C\+\+에서는 기존 MFC 프로젝트를 다음과 같이 수정합니다. 이 예제에서 프로젝트의 이름은 `MFCEXE`입니다.  
  
-   새 파일 두 개\(서버를 등록하는 데 사용한 .idl 파일 및 .rgs 파일\)가 추가됩니다.  
  
-   주 응용 프로그램 헤더 파일과 구현 파일\(Mfcexe.h 및 Mfcexe.cpp\)에서, **CAtlMFCModule**로부터 파생된 새 클래스가 추가됩니다.  새 클래스 외에도 등록을 위해 `InitInstance`에 코드가 추가됩니다.  클래스 개체를 해지하기 위해 `ExitInstance` 함수에도 코드가 추가됩니다.  마지막으로 헤더 파일에서는 새로운 헤더 파일 두 개\(Initguid.h 및 Mfcexe\_i.c\)가 구현 파일에 포함되어 **CAtlMFCModule** 파생 클래스에 대한 새 GUID를 선언하고 초기화합니다.  
  
-   서버를 제대로 등록하기 위해 프로젝트의 리소스 파일에 새 .rgs 파일에 대한 엔트리가 추가됩니다.  
  
## DLL 프로젝트에 대한 참고 사항  
 MFC DLL 프로젝트에 ATL 지원을 추가할 때는 약간 다른 결과가 나타납니다.  DLL을 등록하거나 등록을 취소하기 위해 **DLLRegisterServer** 함수와 **DLLUnregisterServer** 함수에 코드가 추가됩니다.  또한 [DllCanUnloadNow](../Topic/CAtlDllModuleT::DllCanUnloadNow.md) 및 [DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md) 함수에도 코드가 추가됩니다.  
  
## 참고 항목  
 [MFC 프로젝트의 ATL 지원](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../../ide/navigating-the-class-structure-visual-cpp.md)