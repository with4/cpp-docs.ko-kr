---
title: "Windows Vista 공용 컨트롤의 빌드 요구 사항 | Microsoft Docs"
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
  - "공용 컨트롤(MFC)"
  - "공용 컨트롤(MFC), 빌드 요구 사항"
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Windows Vista 공용 컨트롤의 빌드 요구 사항
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft 기반 클래스 \(MFC\) 라이브러리는 Windows 공용 컨트롤 버전 6.1을 지원합니다.  공용 컨트롤에 포함 된 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 라이브러리에 포함 되는 [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)]에 포합됩니다.  새 클래스 및 기존 클래스를 개선 하는 새로운 메서드 및 메서드를 지 원하는 라이브러리를 제공 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 공용 컨트롤입니다.  응용 프로그램을 빌드할 때 다음 단원에서 설명 하는 컴파일 및 마이그레이션 요구 사항을 따라야 합니다.  
  
## 컴파일 요구 사항  
  
### 지원 Version  
 새 클래스 및 메서드 일부 지원만 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 이상 다른 방법 또한 이전 버전의 운영 체제를 지원 합니다.  메모에는  `Requirements`  각 메서드 항목의 경우 필요한 최소 운영 체제를 지정 합니다. [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)].  
  
 컴퓨터 실행 되지 않는 경우에 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]를에서 실행 되는 MFC 응용 프로그램을 빌드할 수 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 컴퓨터에 버전 6.1 MFC 헤더 파일을 사용 하는 경우가 있습니다.  그러나 일반적인 제어 용으로 특별히 디자인 된 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 해당 시스템에 대해서만 작동 하 고 이전 운영 체제에서 무시 됩니다.  
  
### 지원되는 문자 집합  
 새 Windows 공용 컨트롤에 ANSI 문자 집합 및 유니코드 문자 집합만 지원합니다.  명령줄에서 응용 프로그램을 빌드하는 경우 모두 다음과 같은 정의 사용 \(\/ D\) 컴파일러 옵션을 기본으로 유니코드 문자 집합이 있습니다:  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Visual Studio 통합된 개발 환경 \(IDE\)에서 응용 프로그램을 빌드하는 경우 지정 된  **유니코드 문자 집합** 옵션은 **문자 집합** 속성에는 **일반** 프로젝트 속성의 노드가 있습니다.  
  
 여러 가지 MFC 메서드의 ANSI 버전 Windows 공용 컨트롤 버전 6.1부터 시작 되지 않습니다.  자세한 내용은 [사용되지 않는 ANSI API](../mfc/deprecated-ansi-apis.md)을 참조하십시오.  
  
## 데이터 정렬 요구 사항  
 Visual Studio IDE를 사용 하 여 Windows 공용 컨트롤 버전 6.1을 사용 하 여 새 MFC 응용 프로그램 빌드를 IDE는 자동으로 적절 한 매니페스트를 선언 합니다.  그러나 이전 버전의 Visual Studio 기존 MFC 응용 프로그램을 마이그레이션하고 새 공용 컨트롤을 사용 하려는 경우 IDE 제공 하지 않습니다 자동으로 응용 프로그램을 업그레이드 하려면 매니페스트 정보가 있습니다.  대신, stdafx.h 파일에 다음 소스 코드를 수동으로 삽입 해야 합니다.  
  
```  
#ifdef UNICODE  
#if defined _M_IX86  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_IA64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_X64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#else  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#endif  
#endif  
```  
  
## 참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [계층 구조 차트](../mfc/hierarchy-chart.md)   
 [사용되지 않는 ANSI API](../mfc/deprecated-ansi-apis.md)