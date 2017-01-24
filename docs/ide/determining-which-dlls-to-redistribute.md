---
title: "재배포할 DLL 확인 | Microsoft Docs"
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
  - "응용 프로그램 배포[C++], DLL 재배포"
  - "종속성[C++], 응용 프로그램 배포"
  - "응용 프로그램 배포[C++], DLL 재배포"
  - "DLL[C++], 재배포"
  - "DLL 재배포"
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 재배포할 DLL 확인
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio에서 제공하는 DLL을 사용하는 응용 프로그램을 빌드한 경우 응용 프로그램 사용자는 자신의 컴퓨터에 이러한 DLL이 있어야 응용 프로그램을 실행할 수 있습니다.  대부분의 사용자는 Visual Studio가 설치되어 있지 않기 때문에 이러한 DLL을 제공해야 합니다.  Visual Studio는 이러한 DLL을 응용 프로그램 설치 관리자에 포함할 수 있는 재배포 가능 라이브러리로 사용할 수 있도록 해줍니다.  
  
 재배포 가능 DLL은 Visual Studio 설치에 포함되며,  기본적으로 Program Files \(x86\)\\Microsoft Visual Studio version\\VC\\Redist에 설치됩니다.  설치 관리자에 보다 쉽게 포함하려면 Microsoft 다운로드 센터에서 제공하는 독립 실행형 재배포 가능 패키지를 사용하면 됩니다.  이러한 패키지는 사용자의 컴퓨터에 재배포 가능 파일을 설치하는 실행 파일입니다.  재배포 가능 패키지의 버전은 응용 프로그램을 만드는 데 사용한 Visual Studio 도구 집합의 버전과 일치해야 합니다.  일치하는 재배포 가능 패키지를 찾으려면 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?LinkId=158431)에서 "Visual C\+\+ 재배포 가능 패키지"를 검색하세요.  
  
 응용 프로그램과 함께 다시 배포해야 하는 DLL을 결정하려면 응용 프로그램에서 사용되는 DLL 목록을 수집합니다.  목록을 수집하는 한 가지 방법은 [Visual C\+\+ 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)에 설명된 대로 Dependency Walker\(depends.exe\)를 실행하는 것입니다.  
  
 종속성 목록이 있는 경우 Microsoft Visual Studio 설치 디렉터리에 있는 Redist.txt 파일의 목록 또는 Visual Studio에 대한 Microsoft 소프트웨어 사용 약관의 "배포 가능 코드" 단원에 참조된 재배포 가능 DLL의 "REDIST 목록"과 비교합니다.  Visual Studio 2013의 경우 [Microsoft Visual Studio 2013 및 Microsoft Visual Studio 2013 SDK용 배포 가능 코드](http://go.microsoft.com/fwlink/p/?LinkId=313603)에서 온라인으로 목록을 확인할 수 있습니다.  Visual Studio에 포함된 모든 파일을 다시 배포할 수는 없습니다. Redist.txt 또는 온라인 "REDIST 목록"에 지정된 파일만 다시 배포할 수 있습니다. 디버그 버전의 응용 프로그램 및 다양한 Visual C\+\+ 디버그 DLL은 다시 배포할 수 없습니다.  자세한 내용은 [배포 방법 선택](../ide/choosing-a-deployment-method.md)을 참조하세요.  
  
 다음 표에서는 응용 프로그램에서 사용될 수 있는 일부 Visual C\+\+ DLL에 대해 설명합니다.  
  
|Visual C\+\+ 라이브러리|설명|적용 대상|  
|------------------------|--------|-----------|  
|msvcr*version*.dll|네이티브 코드용 CRT\(C 런타임 라이브러리\)|[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)를 사용하는 응용 프로그램|  
|msvcp*version*.dll|네이티브 코드용 표준 C\+\+ 라이브러리|[표준 C\+\+ 라이브러리](../standard-library/cpp-standard-library-reference.md)를 사용하는 응용 프로그램|  
|mfc*version*.dll|MFC\(Microsoft Foundation Class\) 라이브러리|[MFC 라이브러리](../mfc/mfc-desktop-applications.md)를 사용하는 응용 프로그램|  
|mfc*version*u.dll|유니코드를 지원하는 MFC 라이브러리|[MFC 라이브러리](../mfc/mfc-desktop-applications.md)를 사용하고 유니코드 지원이 필요한 응용 프로그램|  
|mfcmifc80.dll|MFC 관리되는 인터페이스 라이브러리|[Windows Forms 컨트롤](../Topic/Windows%20Forms%20Controls.md)과 함께 [MFC 라이브러리](../mfc/mfc-desktop-applications.md)를 사용하는 응용 프로그램|  
|mfcm*version*.dll|MFC 관리되는 라이브러리|[Windows Forms 컨트롤](../Topic/Windows%20Forms%20Controls.md)과 함께 [MFC 라이브러리](../mfc/mfc-desktop-applications.md)를 사용하는 응용 프로그램|  
|mfcm*version*u.dll|유니코드를 지원하는 MFC 관리되는 라이브러리|[Windows Forms 컨트롤](../Topic/Windows%20Forms%20Controls.md)과 함께 [MFC 라이브러리](../mfc/mfc-desktop-applications.md)를 사용하고 유니코드 지원이 필요한 응용 프로그램|  
  
> [!NOTE]
>  더 이상 Active Template Library를 별도의 DLL로 재배포할 필요가 없습니다.  해당 기능은 헤더 및 정적 라이브러리로 이동되었습니다.  
  
 응용 프로그램과 함께 이러한 DLL을 다시 배포하는 방법에 대한 자세한 내용은 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)를 참조하세요.  예제는 [배포 예제](../ide/deployment-examples.md)를 참조하세요.  
  
 일반적으로 시스템 DLL은 운영 체제의 일부이므로 재배포할 필요가 없습니다.  하지만 응용 프로그램이 여러 버전의 Microsoft 운영 체제에서 실행되는 경우와 같은 예외도 있을 수 있습니다.  이 경우 해당 사용 약관을 참조해야 합니다.  또한 Windows 업데이트, 서비스 팩 또는 Microsoft에서 제공하는 재배포 가능 패키지를 통해 업그레이드된 시스템 DLL을 가져오세요.  [Microsoft 지원 웹 사이트](http://support.microsoft.com/) 또는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?LinkId=158431)에서 검색하여 사용 가능한 패키지를 찾을 수 있습니다.  
  
## 참고 항목  
 [배포 방법 선택](../ide/choosing-a-deployment-method.md)   
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)