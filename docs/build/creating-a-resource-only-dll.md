---
title: "리소스 전용 DLL 만들기 | Microsoft Docs"
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
  - "DLL[C++], 만들기"
  - "리소스 전용 DLL[C++], 만들기"
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 리소스 전용 DLL 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스 전용 DLL은 아이콘, 비트맵, 문자열 및 대화 상자 등의 리소스만 들어 있는 DLL입니다.  리소스 전용 DLL을 사용하면 여러 프로그램 간에 동일한 리소스 집합을 쉽게 공유할 수 있습니다.  여러 언어로 지역화된 리소스가 있는 응용 프로그램을 제공하는 것도 좋은 방법입니다\([MFC 응용 프로그램의 지역화된 리소스: 위성 DLL](../build/localized-resources-in-mfc-applications-satellite-dlls.md) 참조\).  
  
 리소스 전용 DLL을 만들려면 새로운 Win32 DLL\(비 MFC\) 프로젝트를 만든 다음 이 프로젝트에 리소스를 추가합니다.  
  
-   **새 프로젝트** 대화 상자에서 Win32 프로젝트를 선택한 다음 Win32 프로젝트 마법사에서 DLL 프로젝트 형식을 지정합니다.  
  
-   해당 DLL에 사용할 문자열 또는 메뉴와 같은 리소스가 포함된 새 리소스 스크립트를 만든 다음 .RC 파일로 저장합니다.  
  
-   **프로젝트** 메뉴에서 **기존 항목 추가**를 선택한 다음 새로 만든 .rc 파일을 프로젝트에 삽입합니다.  
  
-   [\/NOENTRY](../build/reference/noentry-no-entry-point.md) 링커 옵션을 지정합니다. \/NOENTRY 옵션은 링커가 \_main에 대한 참조를 DLL에 링크하지 않도록 하며, 리소스 전용 DLL을 만들 때 반드시 사용해야 합니다.  
  
-   DLL을 빌드합니다.  
  
 리소스 전용 DLL을 사용하는 응용 프로그램은 **LoadLibrary**를 호출하여 [명시적으로 DLL에 링크](../build/loadlibrary-and-afxloadlibrary.md)해야 합니다.  리소스에 액세스하려면 모든 종류의 리소스에 대해 작동하는 일반 함수인 **FindResource** 및 **LoadResource**를 호출하거나 다음과 같은 특정 리소스 관련 함수 중 하나를 호출해야 합니다.  
  
-   `FormatMessage`  
  
-   **LoadAccelerators**  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
 응용 프로그램이 리소스 사용을 마친 경우에는 **FreeLibrary**를 호출해야 합니다.  
  
## 추가 정보  
  
-   [DELETE\_PENDING\_Editing Resources](http://msdn.microsoft.com/ko-kr/c29d31c7-2d94-40ca-8aa0-c7262883529c)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)