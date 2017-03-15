---
title: "/TSAWARE(터미널 서버 인식 응용 프로그램 만들기) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/tsaware"
  - "VC.Project.VCLinkerTool.TerminalServerAware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TSAWARE 링커 옵션"
  - "터미널 서버"
  - "터미널 서버, 터미널 서버 인식 응용 프로그램"
  - "TSAWARE 링커 옵션"
  - "-TSAWARE 링커 옵션"
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /TSAWARE(터미널 서버 인식 응용 프로그램 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TSAWARE[:NO]  
```  
  
## 설명  
 \/TSAWARE 옵션은 프로그램 이미지의 선택적 헤더에 있는 IMAGE\_OPTIONAL\_HEADER DllCharacteristics 필드에 플래그를 설정합니다.  이 플래그가 설정되어 있으면 터미널 서버가 응용 프로그램을 변경하지 않습니다.  
  
 응용 프로그램이 터미널 서버 인식 응용 프로그램\(레거시 응용 프로그램이라고도 함\)이 아니면 터미널 서버에서는 레거시 응용 프로그램이 다중 사용자 환경에서 올바르게 작동하도록 특정 사항을 수정합니다.  예를 들어, 터미널 서버에서는 각 사용자가 시스템의 Windows 디렉터리 대신 Windows 폴더를 사용할 수 있도록 가상 Windows 폴더를 만듭니다.  이렇게 하면 사용자는 자신의 고유 INI 파일에 액세스할 수 있습니다.  또한 터미널 서버에서는 레거시 응용 프로그램에 대한 레지스트리도 약간 수정합니다.  이러한 수정으로 인해 터미널 서버에서 레거시 응용 프로그램의 로드 속도는 느려집니다.  
  
 터미널 서버를 인식하는 응용 프로그램은 설치할 때 INI 파일에 의존해서는 안되며 **HKEY\_CURRENT\_USER** 레지스트리에 기록해서도 안 됩니다.  
  
 \/TSAWARE를 사용하는 경우 응용 프로그램이 계속 INI 파일을 사용하면 해당 파일은 시스템의 모든 사용자가 공유하게 됩니다.  파일을 시스템의 모든 사용자가 공유해도 되면 \/TSAWARE를 사용하여 응용 프로그램을 링크할 수 있으며, 그렇지 않으면 \/TSAWARE:NO를 사용해야 합니다.  
  
 \/TSAWARE 옵션은 Windows 2000 이상, Windows 및 콘솔 응용 프로그램에서 기본적으로 사용됩니다.  자세한 내용은 [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 및 [\/VERSION](../../build/reference/version-version-information.md)을 참조하십시오.  
  
 드라이버, VxD 또는 DLL에는 \/TSAWARE를 사용할 수 없습니다.  
  
 \/TSAWARE를 사용하여 응용 프로그램을 링크한 경우에는 DUMPBIN [\/HEADERS](../../build/reference/headers.md)에서 그 결과에 대한 정보를 표시합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **시스템** 속성 페이지를 클릭합니다.  
  
4.  **터미널 서버** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [Storing User\-Specific Information](http://msdn.microsoft.com/library/aa383452)   
 [Legacy Applications in a Terminal Services Environment](https://msdn.microsoft.com/en-us/library/aa382957.aspx)