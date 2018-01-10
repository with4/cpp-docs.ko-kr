---
title: "MFC의 유니코드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- wide characters, Unicode
- Unicode [MFC], MFC
- wide characters, encoding
- strings [MFC], Unicode
- Unicode [MFC], enabling
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c1a104ffc30a7463d640f63d26f7a80faad333b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="unicode-in-mfc"></a>MFC의 유니코드
MFC는 Windows NT, Windows 2000 및 Windows XP 플랫폼에서 와이드 문자 인코딩을 위한 유니코드 표준을 지원합니다. 유니코드 응용 프로그램은 Windows 98 플랫폼에서 실행할 수 없습니다.  
  
 MFC 라이브러리의 유니코드 버전에 대해서는 아래에서 설명합니다.  
  
### <a name="static-link-libraries"></a>정적 연결 라이브러리  
  
|릴리스|디버그|설명|  
|-------------|-----------|-----------------|  
|UAFXCW.lib, .pdb|UAFXCWD.lib, .pdb|유니코드 MFC 정적 연결 라이브러리|  
  
### <a name="dynamic-link-libraries"></a>동적 연결 라이브러리  
  
|릴리스|디버그|설명|  
|-------------|-----------|-----------------|  
|MFC100U.lib, .dbg, def, .dll, .map, .pdb, .prf|MFC100UD.lib, .def, .dll, .map, .pdb|유니코드 MFC 가져오기 라이브러리(파일 확장명에 대한 설명은 아래 참조)|  
|MFCS100U.lib, .pdb|MFCS100UD.lib, .pdb|응용 프로그램 또는 DLL에 정적으로 연결되어야 하는 코드가 포함된 유니코드 MFC 가져오기 라이브러리|  
  
 **파일 형식**  
  
-   가져오기 라이브러리 파일의 확장자는 .lib입니다.  
  
-   동적 연결 라이브러리 파일의 확장자는 .dll입니다.  
  
-   모듈 정의(.def)파일은 .exe 또는 .dll을 정의하기 위한 문을 포함하는 텍스트 파일입니다.  
  
-   맵(.map) 파일은 프로그램을 링크할 때 링커가 사용하는 정보를 포함하는 텍스트 파일입니다.  
  
-   라이브러리(.lib) 파일은 MFC의 DLL 버전과 함께 사용됩니다. 이러한 파일은 응용 프로그램 또는 DLL에서 정적으로 링크되어야 하는 코드를 포함합니다.  
  
-   프로그램 데이터베이스(.pdb) 파일은 디버깅 및 프로젝트 상태 정보를 포함합니다.  
  
-   디버그(.dbg) 파일은 Visual C++ 디버거에서 사용하는 정보(COFF FPO 및 CodeView)를 포함합니다.  
  
 명명 규칙에 대 한 자세한 내용은 참조 하십시오. [라이브러리 명명 규칙](../mfc/library-naming-conventions.md)합니다.  
  
 MFC에서 유니코드 사용에 대 한 정보를 참조 하십시오. [문자열: 유니코드 및 멀티 바이트 문자 집합 (MBCS) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)

