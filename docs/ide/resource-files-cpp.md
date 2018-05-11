---
title: 리소스 파일 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource files
- resources [C++]
- file types [C++], resource files
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c295b9a3aa4996cdcd2afb17b5a4ff4c90c1159
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-files-c"></a>리소스 파일(C++)
리소스는 사용자에 게 정보를 제공 하는 인터페이스 요소입니다. 비트맵, 아이콘, 도구 모음 및 커서는 모든 리소스. 메뉴에서 선택 하거나 대화 상자에 데이터를 입력 등 작업을 수행 하려면 일부 리소스를 조작할 수 있습니다.  
  
 참조 [리소스 작업](../windows/working-with-resource-files.md) 자세한 정보에 대 한 합니다.  
  
|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projname*.rc|*Projname*|소스 파일|프로젝트에 대 한 리소스 스크립트 파일입니다. 리소스 스크립트 파일 (예: 도구 모음, 대화 상자, 또는 HTML) 프로젝트에 대해 선택한 지원과 프로젝트의 유형에 따라 다음을 포함 되어 있습니다.<br /><br /> 기본 메뉴 정의 합니다.<br />-가속기 및 문자열 테이블<br />-기본 **에 대 한** 대화 상자.<br />-다른 대화 상자입니다.<br />-아이콘 파일 (res\\*Projname*.ico).<br />버전 정보입니다.<br />-비트맵입니다.<br />-도구 모음입니다.<br />HTML 파일입니다.<br /><br /> 리소스 파일에는 표준 Microsoft Foundation 클래스 리소스에 대 한 Afxres.rc 파일이 포함 됩니다.|  
|Resource.h|*Projname*|Header Files|프로젝트에서 사용 하는 리소스에 대 한 정의 포함 하는 리소스 헤더 파일|  
|*Projname*.rc2|*Projname*\res|소스 파일|프로젝트에서 사용 하는 추가 리소스를 포함 하는 스크립트 파일입니다. 프로젝트의.rc 파일 맨 위에 있는.rc2 파일을 포함할 수 있습니다.<br /><br /> .Rc2 파일이 여러 가지 다른 프로젝트에서 사용 하는 리소스를 포함 하는 데 유용 합니다. 다른 프로젝트에 대해 여러 번 같은 리소스를 만드는 대신.rc2 파일에 수 있으며.rc2 파일이 주.rc 파일에 포함.|  
|*Projname*.def|*Projname*|소스 파일|DLL 프로젝트에 대 한 모듈 정의 파일입니다. 컨트롤에 대 한 이름 및 런타임 힙의 크기 뿐 아니라는 컨트롤의 설명을 제공합니다.|  
|*Projname*.ico|*Projname*\res|리소스 파일|프로젝트 또는 컨트롤에 대 한 아이콘 파일입니다. 이 아이콘에는 응용 프로그램 최소화 되었을 때 나타납니다. 응용 프로그램의 사용 되는 **에 대 한** 상자입니다. 기본적으로 MFC 아이콘을 제공 하는 MFC 및 ATL ATL 아이콘을 제공 합니다.|  
|*Projname*데이터|*Projname*\res|리소스 파일|문서/뷰 아키텍처에 대 한 지원을 포함 하는 MFC 프로젝트에 대 한 아이콘 파일입니다.|  
|Toolbar.bmp|*Projname*\res|리소스 파일|응용 프로그램 또는 도구 모음이 나 색상표에서 컨트롤을 나타내는 비트맵 파일입니다. 이 비트맵은 프로젝트의 리소스 파일에 포함 됩니다. 초기 도구 모음 및 상태 표시줄에 생성 되는 **CMainFrame** 클래스입니다.|  
|ribbon.mfcribbon ms|*Projname*\res|리소스 파일|리본 메뉴의 단추, 컨트롤 및 특성을 정의 하는 XML 코드가 포함 하는 리소스 파일입니다. 자세한 내용은 [Ribbon Designer (MFC)](../mfc/ribbon-designer-mfc.md)을 참조하세요.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)