---
title: "리소스 파일(C++) | Microsoft Docs"
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
  - "파일 형식[C++], 리소스 파일"
  - "리소스 파일"
  - "리소스[C++]"
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 리소스 파일(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스는 사용자에게 정보를 제공하는 인터페이스 요소입니다.  비트맵, 아이콘, 도구 모음 및 커서는 모두 리소스입니다.  일부 리소스는 메뉴에서 선택하거나 대화 상자에서 데이터를 입력하는 등의 작업을 수행하도록 조작할 수 있습니다.  
  
 자세한 내용은 [리소스를 사용하여 작업](../mfc/working-with-resource-files.md)을 참조하십시오.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|-----------|-------------|----------------|--------|  
|*Projname*.rc|*Projname*|소스 파일|프로젝트의 리소스 스크립트 파일.  리소스 스크립트 파일에는 프로젝트 형식에 따라 다음 항목이 포함되며 프로젝트에 대해 선택한 지원\(예: 도구 모음, 대화 상자 또는 HTML\)이 포함됩니다.<br /><br /> -   기본 메뉴 정의<br />-   액셀러레이터 키 및 문자열 테이블<br />-   기본 **정보** 대화 상자<br />-   기타 대화 상자<br />-   아이콘 파일\(res\\*Projname*.ico\)<br />-   버전 정보<br />-   비트맵<br />-   도구 모음<br />-   HTML 파일<br /><br /> 리소스 파일에는 표준 Microsoft Foundation Class 리소스에 대한 Afxres.rc 파일이 들어 있습니다.|  
|Resource.h|*Projname*|헤더 파일|프로젝트에서 사용하는 리소스에 대한 정의가 들어 있는 리소스 헤더 파일|  
|*Projname*.rc2|*Projname*\\res|소스 파일|프로젝트에서 사용하는 추가 리소스가 들어 있는 스크립트 파일.  프로젝트의 .rc 파일 맨 위에 .rc2 파일을 포함할 수 있습니다.<br /><br /> .rc2 파일은 서로 다른 여러 프로젝트에서 사용하는 리소스를 넣어두는 데 유용합니다.  여러 프로젝트에서 사용하는 동일한 리소스를 매번 반복해서 만드는 대신 .rc2 파일에 넣고 .rc2 파일을 주 .rc 파일에 포함시킬 수 있습니다.|  
|*Projname*.def|*Projname*|소스 파일|DLL 프로젝트를 위한 모듈 정의 파일.  컨트롤의 경우에는 컨트롤 이름과 설명, 런타임 힙 크기에 대한 정보가 담겨 있습니다.|  
|*Projname*.ico|*Projname*\\res|리소스 파일|프로젝트 또는 컨트롤을 위한 아이콘 파일.  이 아이콘은 응용 프로그램을 최소화할 때 표시됩니다.  또한 응용 프로그램의 **정보** 상자에서도 사용됩니다.  기본적으로 MFC는 MFC 아이콘을, ATL은 ATL 아이콘을 제공합니다.|  
|*Projname*Doc.ico|*Projname*\\res|리소스 파일|문서\/뷰 아키텍처에 대한 지원을 포함하는 MFC 프로젝트를 위한 아이콘 파일|  
|Toolbar.bmp|*Projname*\\res|리소스 파일|도구 모음 또는 팔레트에서 응용 프로그램 또는 컨트롤을 나타내는 비트맵 파일.  이 비트맵은 프로젝트의 리소스 파일에 포함되어 있습니다.  초기 도구 모음과 상태 표시줄은 **CMainFrame** 클래스에서 생성됩니다.|  
|ribbon.mfcribbon\-ms|*Projname*\\res|리소스 파일|리본에 단추, 컨트롤 및 특성을 정의하는 XML 코드가 포함된 리소스 파일.  자세한 내용은 [리본 디자이너\(MFC\)](../mfc/ribbon-designer-mfc.md)를 참조하십시오.|  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)