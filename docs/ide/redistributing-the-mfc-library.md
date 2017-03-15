---
title: "MFC 라이브러리 재배포 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, 재배포"
  - "MFC 라이브러리 재배포"
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# MFC 라이브러리 재배포
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

응용 프로그램을 MFC 라이브러리에 동적으로 연결하는 경우 모든 MFC DLL에서 공유 버전의 CRT\(C 런타임 라이브러리\)를 사용하기 때문에 Msvcr100.dll을 다시 배포해야 합니다.  또한 Mfc100u.dll 또는 Mfc100.dll을 다시 배포해야 합니다.  
  
 응용 프로그램을 MFC에 정적으로 연결하는 경우\(즉, **속성 페이지** 대화 상자의 **일반** 탭에서 **정적 라이브러리에서 MFC 사용** 을 지정하는 경우\)에는 Mfc100u.dll 또는 Mfc100.dll을 다시 배포할 필요가 없습니다.  하지만 응용 프로그램을 테스트하고 내부적으로 배포하는 데는 정적 연결을 사용할 수 있지만 MFC를 다시 배포할 때는 사용하지 않는 것이 좋습니다.  Visual C\+\+ 라이브러리를 배포하는 권장 전략에 대한 자세한 내용은 [배포 방법 선택](../ide/choosing-a-deployment-method.md)을 참조하십시오.  
  
 응용 프로그램에서 WebBrowser 컨트롤을 구현하는 MFC 클래스\(예: [CHtmlView 클래스](../mfc/reference/chtmlview-class.md) 또는 [CHtmlEditView Class](../mfc/reference/chtmleditview-class.md)\)를 사용하는 경우 대상 컴퓨터에 최신 공용 컨트롤 파일이 있도록 최신 버전의 Microsoft Internet Explorer도 설치하는 것이 좋습니다. Internet Explorer 4.0 이상이 필요합니다. Internet Explorer 구성 요소를 설치하는 방법에 대한 자세한 내용은 Microsoft 지원 웹 사이트에서 "문서 185375: Internet Explorer의 단일 EXE 설치를 만드는 방법"을 참조하십시오.  
  
 응용 프로그램에서 MFC 데이터베이스 클래스\(예: [CRecordset Class](../mfc/reference/crecordset-class.md) 및 [CRecordView Class](../mfc/reference/crecordview-class.md)\)를 사용하는 경우 응용 프로그램에서 사용되는 ODBC 및 ODBC 드라이버를 모두 다시 배포해야 합니다.  자세한 내용은 [데이터베이스 지원 파일 재배포](../ide/redistributing-database-support-files.md)을 참조하십시오.  
  
 MFC 응용 프로그램에서 Windows Forms 컨트롤을 사용하는 경우 사용자 응용 프로그램과 함께 mfcmifc80.dll을 재배포해야 합니다.  이 DLL은 응용 프로그램 로컬 폴더에 있는 응용 프로그램과 함께 다시 배포되거나 [Gacutil.exe\(전역 어셈블리 캐시 도구\)](../Topic/Gacutil.exe%20\(Global%20Assembly%20Cache%20Tool\).md)를 사용하여 GAC\(전역 어셈블리 캐시\)에 배포하는 방법으로 다시 배포될 수 있는 강력한 이름으로 서명된 .NET 어셈블리입니다.  
  
 MFC DLL을 다시 배포하는 경우 디버그 버전이 아니라 정품 버전을 다시 배포해야 합니다.  디버그 버전의 DLL은 재배포할 수 없습니다.  디버그 버전의 MFC DLL 이름은 "d"로 끝납니다\(예: Mfc100d.dll\).  
  
 MFC 소스를 수정한 다음 MFC DLL을 다시 빌드하는 경우 Visual Studio에 포함된 MFC DLL과 충돌하지 않도록 수정한 MFC DLL의 이름을 바꾸어야 합니다.  MFC DLL을 다시 빌드하거나 이름을 바꾸지 않는 것이 좋습니다.  자세한 내용은 MFC Technical Note 33을 참조하십시오.  
  
 VCRedist\_*architecture*.exe 또는 Visual Studio와 함께 설치된 병합 모듈을 사용하거나 응용 프로그램과 동일한 폴더에 MFC DLL을 배포하여 MFC를 다시 배포할 수 있습니다.  MFC를 다시 배포하는 방법에 대한 자세한 내용은 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)를 참조하십시오.  
  
## 지역화된 MFC 구성 요소 설치  
 MFC 지역화 DLL을 설치하여 응용 프로그램을 지역화하려는 경우 재배포 가능 병합 파일\(.msm\)을 사용해야 합니다.  예를 들어 x86 컴퓨터에서 응용 프로그램을 지역화하려는 경우 Microsoft\_VC100\_MFCLOC\_x86.msm을 x86 컴퓨터용 설치 패키지에 병합해야 합니다.  
  
 재배포 가능 .msm 파일에는 지역화에 사용되는 DLL이 포함되어 있습니다.  지원되는 각 언어에 대해 DLL 한 개가 있습니다.  설치 프로세스에서 이러한 DLL은 대상 컴퓨터의 %windir%\\system32\\ 폴더에 설치됩니다.  
  
 MFC 응용 프로그램을 지역화하는 방법에 대한 자세한 내용은 [TN057: MFC 구성 요소 지역화](../mfc/tn057-localization-of-mfc-components.md) 및 Microsoft 지원 웹 사이트의 [문서 208983: HOWTO: MFC LOC DLL 사용](http://go.microsoft.com/fwlink/?LinkId=198025) 을 참조하십시오.  
  
 응용 프로그램 로컬 폴더에 MFC DLL을 배포하여 MFC 지역화 DLL을 다시 배포할 수 있습니다.  Visual C\+\+ 라이브러리를 다시 배포하는 방법에 대한 자세한 내용은 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)를 참조하십시오.  
  
## 참고 항목  
 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)