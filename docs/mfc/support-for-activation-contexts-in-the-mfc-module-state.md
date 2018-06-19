---
title: MFC 모듈 상태의 활성화 컨텍스트 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2713e0025c0587a4ab76813d4d07eed0825db447
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380711"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>MFC 모듈 상태의 활성화 컨텍스트 지원
MFC는 사용자 모듈에서 제공되는 매니페스트 리소스를 사용하여 활성화 컨텍스트를 만듭니다. 활성화 컨텍스트를 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [활성화 컨텍스트](http://msdn.microsoft.com/library/aa374153)  
  
-   [응용 프로그램 매니페스트](http://msdn.microsoft.com/library/aa374191)  
  
-   [어셈블리 매니페스트](http://msdn.microsoft.com/library/aa374219)  
  
## <a name="remarks"></a>설명  
 이러한 Windows SDK 항목을 읽을 때 MFC 활성화 컨텍스트 메커니즘 MFC는 Windows SDK 활성화 컨텍스트 API를 사용 하지 않는 제외 하 고 Windows SDK 활성화 컨텍스트 유사한 지 note 합니다.  
  
 활성화 컨텍스트는 다음과 같은 방법으로 MFC 응용 프로그램, 사용자 Dll 및 MFC 확장 Dll에서 작동합니다.  
  
-   MFC 응용 프로그램은 매니페스트 리소스에 대해 리소스 ID 1을 사용합니다. 이 경우 MFC는 자체 활성화 컨텍스트를 만들지 않지만 기본 응용 프로그램 컨텍스트는 사용합니다.  
  
-   MFC 사용자 DLL은 매니페스트 리소스에 대해 리소스 ID 2를 사용합니다. 여기에서 MFC는 각 사용자 DLL에 대해 활성화 컨텍스트를 만들므로 다른 사용자 DLL은 동일한 라이브러리의 다른 버전을 사용합니다(예: 공용 컨트롤 라이브러리).  
  
-   MFC 확장명 DLL은 활성화 컨텍스트를 설정하기 위해 호스팅 응용 프로그램 또는 사용자 DLL을 사용합니다.  
  
 아래 설명 된 프로세스를 사용 하 여 활성화 컨텍스트 상태를 수정할 수 있지만 [활성화 컨텍스트 API를 사용 하 여](http://msdn.microsoft.com/library/aa376620), MFC 활성화 컨텍스트 메커니즘을 사용 하 여 유용 플러그 인 DLL 기반 아키텍처를 개발 하는 경우 없는 쉽게 (받았거나 가능 하지 않은) 직접 외부 플러그 인에 대 한 각 호출 전후의 활성화 상태를 전환 합니다.  
  
 활성화 컨텍스트를에서 만든 [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)합니다. 이러한 활성화 컨텍스트는 `AFX_MODULE_STATE` 소멸자에서 소멸됩니다. 활성화 컨텍스트 핸들은 `AFX_MODULE_STATE`에서 유지됩니다. (`AFX_MODULE_STATE` 에 명시 된 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate).)  
  
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) 매크로 활성화 및 활성화 컨텍스트를 비활성화 합니다. `AFX_MANAGE_STATE`는 정적 MFC 라이브러리와 MFC DLL을 활성화하고 사용자 DLL이 선택한 해당 활성화 컨텍스트에서 실행되도록 MFC 코드를 허용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [활성화 컨텍스트](http://msdn.microsoft.com/library/aa374153)   
 [응용 프로그램 매니페스트](http://msdn.microsoft.com/library/aa374191)   
 [어셈블리 매니페스트](http://msdn.microsoft.com/library/aa374219)   
 [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)   
 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)   
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)

