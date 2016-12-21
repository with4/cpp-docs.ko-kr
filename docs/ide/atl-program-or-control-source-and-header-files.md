---
title: "ATL 프로그램 또는 컨트롤 소스 및 헤더 파일 | Microsoft Docs"
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
  - "파일 형식[C++], ATL 소스 및 헤더"
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 프로그램 또는 컨트롤 소스 및 헤더 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음은 Visual Studio에서 ATL 프로젝트를 만들 때 사용자가 선택하는 옵션에 따라 만들어지는 파일들입니다.  
  
 이 파일들은 모두 *Projname* 디렉터리에 저장되며 솔루션 탐색기의 헤더 파일\(.h 파일\) 폴더 또는 소스 파일\(.cpp 파일\) 폴더 중 하나에 들어 있습니다.  
  
|파일 이름|설명|  
|-----------|--------|  
|*Projname*.h|ATLSample.idl에 정의된 항목의 GUID 선언과 C\+\+ 인터페이스 정의가 들어 있는 주 포함 파일.  컴파일하는 동안 MIDL에 의해 다시 생성됩니다.|  
|*Projname*.cpp|주 프로그램 소스 파일.  in\-process 서버를 위한 DLL의 내보내기 구현 및 로컬 서버를 위한 `WinMain` 구현이 포함되어 있습니다.  서비스의 경우에는 모든 서비스 관리 함수를 추가로 구현합니다.|  
|Resource.h|리소스 파일의 헤더 파일|  
|StdAfx.cpp|StdAfx.h 및 Atlimpl.cpp 파일이 들어 있습니다.|  
|StdAfx.h|ATL 헤더 파일이 들어 있습니다.|  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR 프로젝트](../ide/files-created-for-clr-projects.md)