---
title: "MFC DLL 마법사가 생성하는 클래스 및 함수 | Microsoft Docs"
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
  - "클래스[C++], MFC DLL 마법사로 생성"
  - "코드[C++], MFC DLL 마법사로 생성"
  - "DLL[C++], 마법사 클래스 및 함수"
  - "함수[MFC]"
  - "함수[MFC], DLL"
  - "MFC DLL 마법사"
ms.assetid: e69e62fe-4953-42bf-a2fc-50bbf9bdaeaf
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC DLL 마법사가 생성하는 클래스 및 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC DLL 마법사에서 생성하는 코드는 만들고 있는 DLL의 종류와 선택한 옵션에 따라 달라집니다.  MFC DLL 마법사는 두 가지 종류의 기본 DLL에 대해 같은 코드를 생성합니다.  
  
|DLL 종류|옵션|클래스|함수|  
|------------|--------|---------|--------|  
|[확장명](../../build/extension-dlls-overview.md)|없음|없음|`DllMain`|  
|[기본](../../build/regular-dlls-dynamically-linked-to-mfc.md)|없음|`CWinApp`에서 파생된 응용 프로그램 클래스|없음|  
|[기본](../../build/regular-dlls-dynamically-linked-to-mfc.md)|자동화|`CWinApp`에서 파생된 응용 프로그램 클래스|**DllGetClassObjectDllCanUnloadNowDllRegisterServer**|  
|[확장명](../../build/extension-dlls-overview.md)|Windows 소켓|없음|`DllMain`|  
|[기본](../../build/regular-dlls-dynamically-linked-to-mfc.md)|Windows 소켓|`CWinApp`에서 파생된 응용 프로그램 클래스|`InitInstance`는 `AfxSocketInit`에 대한 호출을 포함합니다.|  
  
## 참고 항목  
 [MFC DLL 마법사](../../mfc/reference/mfc-dll-wizard.md)