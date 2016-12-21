---
title: "MFC의 유니코드 | Microsoft Docs"
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
  - "문자열[C++], Unicode"
  - "유니코드[C++], 사용"
  - "유니코드[C++], MFC"
  - "와이드 문자, 인코딩"
  - "와이드 문자, Unicode"
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC의 유니코드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC는 Windows NT, Windows 2000 및 Windows XP 플랫폼에서 와이드 문자 인코딩을 위한 유니코드 표준을 지원합니다.  유니코드 응용 프로그램은 Windows 98 플랫폼에서는 실행할 수 없습니다.  
  
 MFC 라이브러리의 유니코드 버전은 아래에 설명됩니다.  
  
### 정적 연결 라이브러리  
  
|Release|디버그|설명|  
|-------------|---------|--------|  
|UAFXCW.lib, .pdb|UAFXCWD.lib, .pdb|유니코드 MFC 정적 연결 라이브러리입니다.|  
  
### 동적 연결 라이브러리  
  
|Release|디버그|설명|  
|-------------|---------|--------|  
|MFC100U.lib, .dbg, def, .dll, .map, .pdb, .prf|MFC100UD.lib, .def, .dll, .map, .pdb|유니코드 MFC가 라이브러리를 가져옵니다. \(파일 확장명에 설명은 아래를 참조하세요\)|  
|MFCS100U.lib, .pdb|MFCS100UD.lib, .pdb|유니코드 MFC는 응용 프로그램이나 DLL에서 정적으로 연결되어야 하는 코드를 포함한 라이브러리를 가져옵니다.|  
  
 **파일 형식**  
  
-   확장자\(.lib\)를 가진 라이브러리 파일을 가져옵니다.  
  
-   확장자\(.dll\)를 가진 동적 연결 라이브러리 파일입니다.  
  
-   모듈 정의\(.def\)파일은 .exe 또는 .dll을 정의하기 위한 문을 포함하는 텍스트 파일입니다.  
  
-   MAP\(.Map\) 파일은 프로그램을 링크할 때 링커가 사용하는 정보를 포함하는 텍스트 파일입니다.  
  
-   라이브러리 \(.lib\) 파일은 MFC의 DLL 버전과 함께 사용됩니다.  이러한 파일은 응용 프로그램 또는 DLL에서 정적으로 링크되어야 하는 코드를 포함합니다.  
  
-   프로그램 데이터베이스\(.pdb\) 파일은 디버깅 및 프로젝트 상태 정보를 포함합니다.  
  
-   디버그 \(.dbg\) 파일은 Visual C\+\+ 디버거에서 사용하는 정보\(COFF FPO 및 CodeView\)를 포함합니다.  
  
 명명 규칙에 대한 자세한 정보는 [라이브러리 명명 규칙](../mfc/library-naming-conventions.md)을 참조하십시오.  
  
 MFC를 사용하여 유니코드를 사용하는 것에 대한 자세한 내용은 [Strings: Unicode and Multibyte Character Set \(MBCS\) Support](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)을 참조하십시오.  
  
## 참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)