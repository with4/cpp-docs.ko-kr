---
title: "MFC 라이브러리 버전 자동 링크 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자동 링크[C++]"
  - "MFC의 defaultlib"
  - "링크[C++]"
  - "링크[C++], MFC 라이브러리 버전 자동"
  - "링크[C++], MFC"
  - "MFC 라이브러리, 연결"
  - "MFC 라이브러리, 버전"
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC 라이브러리 버전 자동 링크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 버전 2.0\) \(이전 버전 3.0 이전 버전의 MFC 라이브러리 입력된 목록에서 링커에 대 한 올바른 버전의 MFC 라이브러리를 수동으로 지정 해야 했습니다.  MFC 버전 3.0 이상에서 사용은 MFC 라이브러리 버전을 직접 지정할 필요가 없습니다.  대신 MFC 헤더 파일에서 `#define`**\_DEBUG**나 **\_UNICODE** 등과 같은 전처리기의 정의에 따라 링크할 올바른 버전의 MFC 라이브러리를 자동으로 결정합니다.  MFC 헤더 파일에 **\/defaultlib** 지시문을 추가하여 링커가 특정 버전의 MFC 라이브러리에 링크하도록 합니다.  
  
 예를 들어, 다음 코드는 AFX는에서.H 헤더 파일 중 하나는 NAFXCWD에 링크 하도록 링커에 지시 합니다.LIB 또는 NAFXCW입니다.LIB 버전 중 하나에 MFC의 디버그 버전을 사용 중인지 여부에 따라 다릅니다.  
  
 `#ifndef _UNICODE`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "nafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "nafxcw.lib")`  
  
 `#endif`  
  
 `#else`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "uafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "uafxcw.lib")`  
  
 `#endif`  
  
 `#endif`  
  
 MFC 헤더 파일 MFC 라이브러리, Win32 라이브러리, OLE 라이브러리, 샘플에서 빌드한 OLE 라이브러리, ODBC 라이브러리 등과 같은 필요한 모든 라이브러리에 연결할 수도 있습니다.  Win32 라이브러리는 kernel32.lib와 같이, User32.Lib, 및 GDI32.Lib를 포함합니다.  
  
## 참고 항목  
 [MFC 라이브러리 버전](../mfc/mfc-library-versions.md)