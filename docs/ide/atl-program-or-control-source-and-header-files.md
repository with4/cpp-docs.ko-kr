---
title: "ATL 프로그램 또는 컨트롤 소스 및 헤더 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a13a4c6ddb74a6f63b5da1171a3d4360199b508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL 프로그램 또는 컨트롤 소스 및 헤더 파일
만들 프로젝트에 대 한 선택 옵션에 따라 Visual Studio에서 ATL 프로젝트를 만들 때에 다음 파일이 생성 됩니다.  
  
 에 살고 있는 모든이 파일은 *Projname* 디렉터리 및 헤더 (.h) 파일 폴더 또는 솔루션 탐색기에서 소스 파일 (.cpp 파일) 폴더에 있습니다.  
  
|파일 이름|설명|  
|---------------|-----------------|  
|*Projname*.h|C + + 인터페이스 정 및 ATLSample.idl에 정의 된 항목의 GUID 선언이 포함 된 주요 포함 파일입니다. 컴파일 중 MIDL에 의해 다시 생성 됩니다.|  
|*Projname*.cpp|주 프로그램 소스 파일입니다. 구현 및 DLL의 내보내기 프로세스 서버에 대 한 구현을 포함 `WinMain` 로컬 서버에 대 한 합니다. 서비스에 대 한 모든 서비스 관리 기능 추가로 구현 합니다.|  
|Resource.h|리소스 파일에 대 한 헤더 파일입니다.|  
|StdAfx.cpp|StdAfx.h 및 Atlimpl.cpp 파일을 포함합니다.|  
|StdAfx.h|ATL 헤더 파일에 포함 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR 프로젝트](../ide/files-created-for-clr-projects.md)