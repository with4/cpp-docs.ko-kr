---
title: "MFC DLL 마법사, 응용 프로그램 설정 | Microsoft Docs"
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
  - "vc.appwiz.mfc.dll.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC DLL 마법사, 응용 프로그램 설정"
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC DLL 마법사, 응용 프로그램 설정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC DLL 마법사의 이 페이지에서는 새 MFC DLL 프로젝트를 설계하고 기본적인 기능을 추가합니다.  
  
## DLL 형식  
 만들려는 DLL 형식을 선택합니다.  
  
 **공유 MFC DLL을 사용하는 기본 DLL**  
 프로그램에 공유 DLL로 MFC 라이브러리를 연결하려면 이 옵션을 선택합니다.  이 옵션을 사용하면 DLL과 호출하는 응용 프로그램 간에 MFC 개체를 공유할 수 없습니다.  프로그램에서는 런타임에 MFC 라이브러리를 호출합니다.  이 옵션을 선택하면 MFC 라이브러리를 사용하는 여러 개의 실행 파일로 구성된 프로그램에 대한 디스크 및 메모리 요구 사항이 줄어듭니다.  Win32 및 MFC 프로그램 모두 DLL에서 함수를 호출할 수 있습니다.  이러한 형식의 프로젝트로 MFC DLL을 다시 배포해야 합니다.  
  
 **MFC를 정적으로 링크한 기본 DLL**  
 빌드할 때 프로그램을 MFC 라이브러리에 정적으로 연결하려면 이 옵션을 선택합니다.  Win32 및 MFC 프로그램 모두 DLL에서 함수를 호출할 수 있습니다.  이 옵션을 사용하면 프로그램 크기는 커지지만 이러한 형식의 프로젝트로 MFC DLL을 다시 배포할 필요가 없습니다.  DLL과 호출하는 응용 프로그램 간에 MFC 개체를 공유할 수 없습니다.  
  
 **MFC 확장 DLL**  
 프로그램에서 런타임에 MFC 라이브러리를 호출하고 DLL과 호출하는 응용 프로그램 사이에 MFC 개체를 공유하도록 하려면 이 옵션을 선택합니다.  이 옵션을 사용하면 MFC 라이브러리를 사용하는 여러 개의 실행 파일로 구성된 프로그램에 대한 디스크 및 메모리 요구 사항이 줄어듭니다.  MFC 프로그램만 DLL에서 함수를 호출할 수 있습니다.  이러한 형식의 프로젝트로 MFC DLL을 다시 배포해야 합니다.  
  
## 추가 기능  
 MFC DLL이 자동화 및 Windows 소켓을 지원해야 하는지 여부를 선택합니다.  
  
 **자동화**  
 다른 프로그램에서 구현된 개체를 프로그램에서 조작할 수 있게 하려면 **자동화**를 선택합니다.  또한 이 옵션을 선택하면 프로그램이 다른 자동화 클라이언트에 노출됩니다.  자세한 내용은 [자동화](../../mfc/automation.md)를 참조하십시오.  
  
 **Windows 소켓**  
 프로그램이 Windows 소켓을 지원하도록 하려면 이 옵션을 선택합니다.  Windows 소켓을 사용하면 TCP\/IP 네트워크를 통해 통신하는 프로그램을 작성할 수 있습니다.  
  
 Windows 소켓을 지원하는 MFC DLL을 만들면 [CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md)가 소켓 지원을 초기화하고 MFC 헤더 파일 StdAfx.h에 AfxSock.h가 포함됩니다.  
  
## 참고 항목  
 [MFC DLL 마법사](../../mfc/reference/mfc-dll-wizard.md)   
 [MFC DLL 프로젝트 만들기](../../mfc/reference/creating-an-mfc-dll-project.md)