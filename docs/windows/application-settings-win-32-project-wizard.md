---
title: "Win32 프로젝트 마법사, 응용 프로그램 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.win32.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 설정[C++]"
  - "Win32 프로젝트 마법사, 응용 프로그램 설정"
ms.assetid: d6b818f0-9b23-4793-a6c5-df1c8c594bad
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Win32 프로젝트 마법사, 응용 프로그램 설정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 마법사 페이지에서는 Win32 프로젝트에 대한 옵션을 설정합니다.  
  
 **응용 프로그램 종류**  
 지정된 형식의 응용 프로그램을 만듭니다.  
  
|옵션|설명|  
|--------|--------|  
|**콘솔 응용 프로그램**|콘솔 응용 프로그램을 만듭니다.  콘솔 프로그램은 콘솔 창에서 문자 모드를 지원하는 [Console 함수](https://msdn.microsoft.com/en-us/library/ms813137.aspx)를 사용하여 개발됩니다.  또한 Visual C\+\+ [run\-time libraries](../c-runtime-library/c-run-time-library-reference.md)에서는 **printf s\(\)** 및 **scanf s\(\)**와 같은 표준 I\/O 함수를 사용하여 콘솔 창의 입출력을 제공합니다.  콘솔 응용 프로그램에는 그래픽 사용자 인터페이스가 없습니다.  콘솔 응용 프로그램은 .exe 파일로 컴파일되며 명령줄에서 독립 응용 프로그램으로 실행할 수 있습니다.<br /><br /> 콘솔 응용 프로그램에 MFC 및 ATL 지원을 추가할 수 있습니다.|  
|**Windows 응용 프로그램**|Win32 프로그램을 만듭니다.  Win32 프로그램은 C 또는 C\+\+로 작성된 실행 응용 프로그램\(EXE\)으로, Win32 API를 호출하여 그래픽 사용자 인터페이스를 만듭니다.<br /><br /> Windows 응용 프로그램에는 MFC나 ATL 지원을 추가할 수 없습니다.|  
|**DLL**|Win32 동적 연결 라이브러리\(DLL\)를 만듭니다.  Win32 DLL은 C나 C\+\+로 작성된 이진 파일로서, MFC 클래스 대신 Win32 API 호출을 사용하며 여러 응용 프로그램에서 동시에 사용할 수 있는 공유 함수 라이브러리 역할을 합니다.<br /><br /> DLL 응용 프로그램에는 MFC나 ATL 지원을 추가할 수 없습니다.  DLL에서 기호를 내보내도록 지정할 수 있습니다.|  
|**정적 라이브러리**|정적 라이브러리를 만듭니다.  정적 라이브러리는 개체 및 그 함수, 실행 파일이 빌드될 때 프로그램에 연결되는 데이터 등이 들어 있는 파일입니다.  이 항목에서는 정적 라이브러리의 기초 파일과 [프로젝트 속성](../ide/property-pages-visual-cpp.md)을 만드는 방법을 설명합니다.  정적 라이브러리 파일은 다음과 같은 이점을 제공합니다.<br /><br /> -   Win32 정적 라이브러리는 작업 중인 응용 프로그램이 MFC 클래스가 아닌 Win32 API를 호출하는 경우 유용합니다.<br />-   나머지 Windows 응용 프로그램이 C와 C\+\+로 작성된 경우 연결 프로세스는 동일합니다.<br />-   MFC 기반 프로그램과 MFC 기반이 아닌 모든 프로그램에 정적 라이브러리를 연결할 수 있습니다.|  
  
 **추가 옵션**  
 응용 프로그램 형식에 따라 응용 프로그램에 대한 지원 및 옵션을 정의합니다.  
  
|옵션|설명|  
|--------|--------|  
|**빈 프로젝트**|프로젝트 파일이 비어 있도록 지정합니다.  .cpp 파일, 헤더 파일, 아이콘, 도구 모음, 대화 상자와 같은 소스 코드 파일이 있을 경우 Visual C\+\+ 개발 환경에서 프로젝트를 만들려면 먼저 빈 프로젝트를 만든 다음 파일을 프로젝트에 추가해야 합니다.<br /><br /> 이 옵션은 정적 라이브러리 프로젝트에는 사용할 수 없습니다.|  
|**내보내기 기호**|DLL 프로젝트에서 기호를 내보내도록 지정합니다.|  
|**미리 컴파일된 헤더**|정적 라이브러리 프로젝트에서 미리 컴파일된 헤더를 사용하도록 지정합니다.|  
|SDL\(Security Development Lifecycle\) 검사\(C\)|SDL에 대한 자세한 정보는 [Microsoft Security Development Lifecycle \(SDL\)  Process Guidance](84aed186-1d75-4366-8e61-8d258746bopq)를 참조하십시오.|  
  
 **다음을 지원**  
 Visual C\+\+에서 제공되는 라이브러리 중 하나에 대한 지원을 추가합니다.  
  
|옵션|설명|  
|--------|--------|  
|**ATL**|프로젝트에 ATL\(Active Template Library\)의 클래스에 대한 지원을 포함합니다.  이 옵션은 Win32 콘솔 응용 프로그램에서만 사용할 수 있습니다.<br /><br /> **참고** 이 옵션은 ATL 코드 마법사를 사용하여 ATL 개체를 추가하는 작업을 지원하지는 않습니다.  ATL 개체는 ATL 프로젝트와 ATL을 지원하는 MFC 프로젝트에만 추가할 수 있습니다.|  
|**MFC**|프로젝트에 MFC\(Microsoft Foundation Class\) 라이브러리에 대한 지원을 포함합니다.  이 옵션은 Win32 콘솔 응용 프로그램과 정적 라이브러리에서만 사용할 수 있습니다.|  
  
## 참고 항목  
 [Win32 응용 프로그램 마법사](../windows/win32-application-wizard.md)   
 [방법: Windows 데스크톱 응용 프로그램 만들기](../Topic/How%20to:%20Create%20a%20Windows%20Desktop%20Application.md)