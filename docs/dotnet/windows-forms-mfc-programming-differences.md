---
title: "Windows Forms/MFC 프로그래밍의 차이점 | Microsoft Docs"
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
  - "MFC[C++], Windows Forms 지원"
  - "Windows Forms[C++], MFC와 비교"
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Forms/MFC 프로그래밍의 차이점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)의 항목에서는 Windows Forms에 대한 MFC 지원을 설명합니다.  .NET Framework 또는 MFC 프로그래밍에 익숙하지 않으면 이 항목에서 두 프로그래밍 방식 사이의 차이점에 대한 배경 지식을 얻을 수 있습니다.  
  
 Windows Forms은 .NET Framework에서 Microsoft Windows 응용 프로그램을 만들기 위한 것입니다.  이 프레임워크는 현대적이고 개체 지향적이며 확장 가능한 클래스 집합을 제공하므로 Windows 기반의 강력한 응용 프로그램을 개발할 수 있습니다.  Windows Forms을 사용하면 광범위한 데이터 소스에 액세스하고 Windows Forms 컨트롤을 통해 데이터 표시 및 데이터 편집 기능을 제공하는 강력한 클라이언트 응용 프로그램을 만들 수 있습니다.  
  
 그러나 MFC에 익숙한 개발자는 Windows Forms에서는 아직 명시적으로 지원되지 않는 종류의 응용 프로그램을 주로 만들었을 것입니다.  Windows Forms 응용 프로그램은 MFC 대화 상자 응용 프로그램에 해당합니다.  그러나 Windows Forms 응용 프로그램은 OLE 문서 서버\/컨테이너, ActiveX 문서, SDI\(단일 문서 인터페이스\), MDI\(다중 문서 인터페이스\), MTI\(다중 최상위 인터페이스\)에 대한 문서\/뷰 지원 등 다른 종류의 MFC 응용 프로그램을 직접 지원하기 위한 인프라를 제공하지 않습니다.  이러한 응용 프로그램은 고유의 논리를 작성하여 만들 수 있습니다.  
  
 Windows Forms 응용 프로그램에 대한 자세한 내용은 [Windows Forms 소개](../Topic/Windows%20Forms%20Overview.md)를 참조하십시오.  
  
 MFC와 함께 사용 하는 Windows Forms을 보여 주는 샘플 응용 프로그램은 [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)을 참조하십시오.  
  
 Windows Forms에는 다음의 MFC 뷰 또는 문서 및 명령 라우팅 기능에 해당하는 기능이 없습니다.  
  
-   셸 통합  
  
     MFC에서는 사용자가 문서를 마우스 오른쪽 단추로 클릭하고 열기, 편집 또는 인쇄와 같은 동사를 선택할 때 셸에서 사용하는 DDE\(동적 데이터 교환\) 명령 및 명령줄 인수를 처리합니다.  Windows Forms에서는 셸 통합을 사용하지 않으므로 셸 동사에 응답하지 않습니다.  
  
-   문서 템플릿  
  
     MFC에서는 문서 템플릿이 프레임 창\(MDI, SDI 또는 MTI 모드\)에 포함된 뷰를 사용자가 연 문서와 연결합니다.  Windows Forms에는 문서 템플릿에 해당하는 기능이 없습니다.  
  
-   문서  
  
     MFC에서는 문서 파일 형식을 등록하고 셸에서 문서를 열 때 문서 형식을 처리합니다.  Windows Forms에서는 문서를 지원하지 않습니다.  
  
-   문서 상태  
  
     MFC에서는 문서의 변경 상태를 유지합니다.  따라서 응용 프로그램을 닫고 응용 프로그램이 포함된 마지막 뷰를 닫거나 Windows를 끝내면 문서를 저장하라는 메시지가 나타납니다.  Windows Forms에서는 이에 해당하는 기능을 지원하지 않습니다.  
  
-   명령  
  
     MFC에서는 명령이라는 개념을 사용합니다.  메뉴 모음, 도구 모음 및 상황에 맞는 메뉴는 모두 같은 명령\(예: 잘라내기 및 복사\)을 호출합니다.  Windows Forms에서는 명령이 메뉴 항목과 같은 특정 UI 요소로부터 발생하는 경계가 뚜렷한 이벤트이므로 모든 명령 이벤트를 명시적으로 후크해야 합니다.  Windows Forms에서는 여러 개의 이벤트를 한 개의 처리기로 처리할 수 있습니다.  자세한 내용은 [Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결](../Topic/How%20to:%20Connect%20Multiple%20Events%20to%20a%20Single%20Event%20Handler%20in%20Windows%20Forms.md)을 참조하십시오.  
  
-   명령 라우팅  
  
     MFC 명령 라우팅은 활성 뷰나 문서에서 명령을 처리할 수 있도록 합니다.  MFC에서는 같은 명령이라도 뷰마다 의미가 다른 경우가 많습니다. 예를 들어, 텍스트 편집 뷰와 그래픽 편집기에서 복사 명령이 서로 다른 방식으로 작동합니다. 따라서 활성 뷰에서 명령을 처리해야 합니다.  Windows Forms의 메뉴와 도구 모음에는 원래 활성 뷰라는 개념이 없으므로 **MenuItem.Click** 이벤트에 대해 각 뷰 형식마다 다른 처리기를 사용할 수 없습니다. 그렇게 하려면 내부 코드를 추가로 작성해야 합니다.  
  
-   명령 업데이트 메커니즘  
  
     MFC에는 명령 업데이트 메커니즘이 있습니다.  따라서 활성 뷰나 문서에서 UI 요소의 상태\(예: 메뉴 항목 또는 도구 단추의 활성\/비활성 상태 및 선택 상태 등\)를 담당합니다.  Windows Forms에는 명령 업데이트 메커니즘에 해당하는 기능이 없습니다.  
  
## 참고 항목  
 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms Walkthroughs](http://msdn.microsoft.com/ko-kr/fd44d13d-4733-416f-aefc-32592e59e5d9)