---
title: 미리 컴파일된 헤더 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- stdafx.h
dev_langs:
- C++
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4595ea9ce27c40fb798ac050ce456c4d43b2cacb
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33328089"
---
# <a name="precompiled-header-files"></a>미리 컴파일된 헤더 파일
이러한 파일은 미리 컴파일된 헤더 파일 *Projname*.pch와 미리 컴파일된 형식 파일 Stdafx.obj를 빌드하는 데 사용됩니다.  
  
 이러한 파일은 *Projname* 디렉터리에 있습니다. 솔루션 탐색기에서 Stdafx.h는 헤더 파일 폴더에 있고 Stdafx.cpp는 원본 파일 폴더에 있습니다.  
  
|파일 이름|설명|  
|---------------|-----------------|  
|stdafx.h|표준 시스템 포함 파일 및 자주 사용되지만 자주 변경되지 않는 프로젝트 관련 포함 파일에 대한 포함 파일입니다.<br /><br /> stdafx.h에서는 _AFX_NO_XXX 매크로를 정의하거나 정의 해제해서는 안 됩니다. 기술 자료 문서 "PRB: _AFX_NO_XXX를 정의하는 동안 문제 발생"을 참조하세요. 기술 자료 문서는 MSDN 라이브러리 또는 [http:// support.microsoft.com/](http://%20support.microsoft.com/)에서 찾을 수 있습니다.|  
|stdafx.cpp|전처리기 지시문 `#include "stdafx.h"` 를 포함하며 미리 컴파일된 형식에 대한 포함 파일을 추가합니다. 헤더 파일을 비롯한 모든 형식의 미리 컴파일된 파일은 필요한 파일로만 컴파일을 제한하여 보다 빠른 컴파일 시간을 지원합니다. 처음으로 프로젝트를 빌드하고 나면 미리 컴파일된 헤더 파일이 있기 때문에 이후 빌드 시간이 훨씬 더 빨라짐을 확인할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)   
 [프로젝트 속성 사용](../ide/working-with-project-properties.md)