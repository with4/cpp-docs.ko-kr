---
title: "Windows Vista 공용 컨트롤의 빌드 요구 사항 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76919bcdd416ed7195e94ed1fa0b2e3f3a4d573d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Windows Vista 공용 컨트롤의 빌드 요구 사항
MFC(Microsoft Foundation Class) 라이브러리는 Windows 공용 컨트롤 버전 6.1을 지원합니다. 공용 컨트롤은 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]에 포함되며, 라이브러리는 [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)]에 포함됩니다. 라이브러리에서 기존 클래스 및 새 클래스를 향상 시키는 새로운 메서드와 지 원하는 메서드를 제공 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 공용 컨트롤입니다. 응용 프로그램을 빌드할 때는 다음 섹션에 설명된 컴파일 및 마이그레이션 요구 사항을 따라야 합니다.  
  
## <a name="compilation-requirements"></a>컴파일 요구 사항  
  
### <a name="supported-versions"></a>지원되는 버전  
 일부 새 클래스 및 메서드에서는 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 이상만 지원되지만 다른 메서드에서는 이전 버전의 운영 체제도 지원됩니다. 각 메서드 항목의 `Requirements` 섹션에는 필요한 최소 운영 체제가 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]인 경우 그에 대한 알림이 표시되어 있습니다.  
  
 컴퓨터 실행 되지 않는 경우에 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]에서 실행 되는 MFC 응용 프로그램을 빌드할 수 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 컴퓨터에 버전 6.1 MFC 헤더 파일을 사용 하는 경우. 그러나 공통 제어 용으로 특별히 설계 [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] 해당 시스템에 대해서만 작동 하 고 이전 버전의 운영 체제에서 무시 됩니다.  
  
### <a name="supported-character-sets"></a>지원되는 문자 집합  
 새로운 Windows 공용 컨트롤에서는 ANSI 문자 집합이 아닌 유니코드 문자 집합만 지원됩니다. 명령 줄에서 응용 프로그램을 빌드할 때는 다음 정의 컴파일러 옵션(/D)을 모두 사용해서 기본 문자 집합으로 유니코드를 지정합니다.  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Visual Studio 통합된 개발 환경 (IDE)에서 응용 프로그램을 빌드할 경우 지정 된 **유니코드 문자 집합** 옵션의는 **문자 집합** 속성에는 **일반**  프로젝트 속성의 노드.  
  
 ANSI 버전으로 된 일부 MFC 메서드는 Windows 공용 컨트롤 버전 6.1부터 더 이상 사용되지 않습니다. 자세한 내용은 참조 [사용 되지 않는 ANSI Api](../mfc/deprecated-ansi-apis.md)합니다.  
  
## <a name="migration-requirements"></a>마이그레이션 요구 사항  
 Visual Studio IDE를 사용해서 Windows 공용 컨트롤 버전 6.1을 사용하는 새로운 MFC 응용 프로그램을 빌드할 경우, IDE가 적절한 매니페스트를 자동으로 선언합니다. 하지만 이전 버전의 Visual Studio에서 기존 MFC 응용 프로그램을 마이그레이션하고 새로운 공용 컨트롤을 사용하려는 경우에는 IDE가 응용 프로그램을 업그레이드하기 위한 매니페스트 정보를 자동으로 제공하지 않습니다. 대신 stdafx.h 파일에 다음 소스 코드를 수동으로 삽입해야 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [계층 구조 차트](../mfc/hierarchy-chart.md)   
 [사용되지 않는 ANSI API](../mfc/deprecated-ansi-apis.md)

