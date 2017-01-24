---
title: "AFXDLL 버전 | Microsoft Docs"
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
  - "afxdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL 라이브러리"
  - "응용 프로그램 마법사[C++], 기본값으로 AFXDLL 사용"
  - "MFC의 DLL 버전[C++]"
  - "MFC[C++], AFXDLL 버전"
  - "MFC DLL[C++], 라이브러리에 동적 연결"
  - "MFC 라이브러리[C++], 동적 링크"
ms.assetid: c078ae8f-85a9-43cb-9ded-c09ca2c45723
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AFXDLL 버전
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Instead of building your application by statically linking to the MFC object\-code libraries, you can build your application to use one of the AFXDLL libraries, which contain MFC in a DLL that multiple running applications can share.  For a table of AFXDLL names, see [DLLs: Naming Conventions](../build/naming-conventions-for-mfc-dlls.md).  
  
> [!NOTE]
>  By default, the MFC Application Wizard creates an AFXDLL project.  To use static linking of MFC code instead, set the **Use MFC in a static library** option in the MFC Application Wizard.  Static linking is not available in the Standard Edition of Visual C\+\+.  
  
## 참고 항목  
 [MFC 라이브러리 버전](../mfc/mfc-library-versions.md)