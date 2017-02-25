---
title: "원격 자동화 연결 관리자 | Microsoft Docs"
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
  - "자동화 클라이언트, 원격 자동화를 위한 구성"
  - "자동화 서버, 원격 자동화를 위한 구성"
  - "RAC 관리자 도구"
  - "레지스트리, 원격 자동화"
  - "원격 자동화 연결 관리자"
  - "원격 자동화, 클라이언트 및 서버 컴퓨터 구성"
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 원격 자동화 연결 관리자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

To configure both client and server machines, you need to make registry changes.  Rather than doing this by hand, it is far easier to use the Remote Automation Connection \(RAC\) Manager tool.  This tool, RACMGR32.EXE, along with RACREG32.DLL, needs to be copied to any directory you choose.  By putting it in the PATH, it can be executed from the taskbar using Run.  Alternatively, you can create a shortcut to it or place a reference to it on the Start menu.  
  
 RACMGR32 is written in Visual Basic and therefore needs some Visual Basic support DLLs.  These files are placed in the same directory as RACMGR32.EXE on the CD\-ROM.  The versions of these files that are installed by the Setup for Visual C\+\+ Enterprise Edition are equivalent or more recent than those that shipped with Visual Basic Enterprise Edition 5.0.  The Visual C\+\+ Setup copies the new versions of the Visual Basic files to your system directory.  For Windows 9x, this directory is typically C:\\Windows\\System.  For Windows NT and Windows 2000, it is typically C:\\WINNT\\system32.  Setup also registers these files with the operating system.  You may remove them from your Visual Basic installation.  
  
## 참고 항목  
 [자동화 관리자\(MFC\)](../mfc/automation-manager-mfc.md)   
 [원격 자동화 사용자 구성 요소](../mfc/remote-automation-user-components.md)   
 [원격 자동화 설치](../mfc/remote-automation-installation.md)