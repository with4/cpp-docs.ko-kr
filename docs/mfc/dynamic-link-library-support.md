---
title: "동적 연결 라이브러리 지원 | Microsoft Docs"
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
  - "DLL[C++], MFC"
  - "MFC DLL[C++], 기본 DLL"
  - "NAFXDW.LIB"
  - "NAFXDWD.LIB"
  - "기본 DLL[C++], 프로젝트 대상을 DLL로"
  - "USRDLL, DLL 지원"
ms.assetid: cc31c69f-3c78-4db1-9ecd-0fd8dc3217e3
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 동적 연결 라이브러리 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The NAFXCW.lib and NAFXCWD.lib libraries \(listed in the Static\-Link Library Naming Conventions table in [Library Naming Conventions](../mfc/library-naming-conventions.md)\) create your project as a dynamic\-link library, called a "Regular DLL" \(formerly a "USRDLL"\) that can be used with applications not built with the class library.  This DLL support is not the same as MFCx0.DLL and MFCx0D.DLL \(known as AFXDLL\), which contain the entire class library in a DLL.  자세한 내용은 [DLLs](../build/dlls-in-visual-cpp.md)을 참조하십시오.  For a table of DLL names, see [Naming Conventions for MFC DLLs](../build/naming-conventions-for-mfc-dlls.md).  
  
## 참고 항목  
 [MFC 라이브러리 버전](../mfc/mfc-library-versions.md)