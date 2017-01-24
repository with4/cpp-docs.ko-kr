---
title: "MFC 모듈 상태의 활성화 컨텍스트 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "활성화 컨텍스트[C++]"
  - "활성화 컨텍스트[C++], MFC 지원"
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC 모듈 상태의 활성화 컨텍스트 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 는 사용자 모듈에서 제공되는 매니페스트 리소스를 사용하는 활성화 컨텍스트를 만듭니다.  활성화 컨텍스트를 만드는 방법에 대한 자세한 내용은, 다음 항목을 참조하세요:  
  
-   [Activation Contexts](http://msdn.microsoft.com/library/aa374153)  
  
-   [Application Manifests](http://msdn.microsoft.com/library/aa374191)  
  
-   [Assembly Manifests](http://msdn.microsoft.com/library/aa374219)  
  
## 설명  
 이러한 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] 항목들을 읽을 때, [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] 활성화 컨텍스트 API를 사용하지 않는 MFC를 제외하고 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] 활성화 컨텍스트와 유사한 MFC 활성화 컨텍스트 메커니즘을 기록합니다.  
  
 활성화 컨텍스트은 다음과 같은 방식으로 MFC 응용 프로그램, 사용자 DLL들과 확장 DLL들에서 작동합니다:  
  
-   MFC 응용 프로그램은 그들의 매니페스트 리소스에 대한 리소스 ID를 1로 사용합니다.  이 경우, MFC는 자체 활성화 컨텍스트를 만들지 않지만, 사용자는 기본 응용프로그램 컨텍스트를 사용합니다.  
  
-   MFC 사용자 DLL은 그들의 매니페스트 리소스에 대한 리소스 ID를 2로 사용합니다.  여기에서, MFC는 각 사용자 DLL에 대한 활성화 컨텍스트를 만들고, 다른 사용자 DLL은 같은 라이브러리의 다른 버전들을 사용합니다.\(예를들어, 공통 컨트롤 라이브러리\)  
  
-   MFC 확장 DLL은 활성화 컨텍스트를 설정하기 위해 사용자 DLL 또는 호스팅 응용프로그램들에 의존합니다.  
  
 활성화 컨텍스트 상태는 [Using the Activation Context API](http://msdn.microsoft.com/library/aa376620) 아래에서 설명된 프로세스를 사용하여 변경될 수 있지만, MFC 활성화 컨텍스트 메커니즘은 개발 DLL 기반 플러그인 아키텍처가 외부 플러그인에서 개별적으로 호출된 후나 전에 활성화 상태를 전환 할때, 유용하게 사용됩니다.  
  
 [AfxWinInit](../Topic/AfxWinInit.md) 에서 활성화 컨텍스트가 만들어집니다.  이것은 `AFX_MODULE_STATE` 소멸자에서 소멸됩니다.  `AFX_MODULE_STATE` 에서 처리된 활성화 컨텍스트 핸들입니다. \(`AFX_MODULE_STATE` 은 [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md)에서 설명됩니다.\)  
  
 [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) 매크로는 활성화 컨텍스트를 활성화및 비활성화 합니다.  `AFX_MANAGE_STATE` 는 정적 MFC 라이브러리와 MFC DLL들을 활성화할 뿐만 아니라 사용자 DLL로부터 선택된 적합한 활성화 컨테스트에서 실행되도록 MFC코드를 허용합니다.  
  
## 참고 항목  
 [Activation Contexts](http://msdn.microsoft.com/library/aa374153)   
 [Application Manifests](http://msdn.microsoft.com/library/aa374191)   
 [Assembly Manifests](http://msdn.microsoft.com/library/aa374219)   
 [AfxWinInit](../Topic/AfxWinInit.md)   
 [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md)   
 [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md)