---
title: "방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC[C++], Windows Forms 컨트롤"
  - "Windows Forms[C++], MFC 지원"
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# 방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 단계에서는 .NET Framework 사용자 정의 컨트롤을 만들고 \(특히 Windows 컨트롤 라이브러리 프로젝트의 경우\) 컨트롤 클래스 라이브러리에서 사용자 정의 컨트롤을 작성한 다음 프로젝트를 어셈블리로 컴파일하는 방법을 보여 줍니다.  그런 다음 [CView Class](../mfc/reference/cview-class.md) 및 [CWinFormsView Class](../mfc/reference/cwinformsview-class.md)에서 파생된 클래스를 사용하는 MFC 응용 프로그램에서 이 컨트롤을 사용합니다.  
  
 Windows Forms 사용자 정의 컨트롤을 만들고 컨트롤 클래스 라이브러리를 작성하는 방법에 대한 자세한 내용은 [방법: 합성 컨트롤 제작](../Topic/How%20to:%20Author%20Composite%20Controls.md)을 참조하십시오.  
  
> [!NOTE]
>  때로는 타사 Grid 컨트롤 같은 Windows Forms 컨트롤이 MFC 응용 프로그램에 호스팅된 경우 올바르게 작동하지 않을 수 있습니다.  이 문제를 해결하려면 Windows Forms 사용자 정의 컨트롤을 MFC 응용 프로그램에 추가한 다음 타사 Grid 컨트롤을 이 사용자 정의 컨트롤 안에 배치하는 것이 좋습니다.  
  
 이 절차에서는 [방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)에 나와 있는 설명에 따라 WindowsFormsControlLibrary1이라는 Windows Forms 컨트롤 라이브러리 프로젝트를 만든 것으로 가정합니다.  
  
### MFC 호스트 응용 프로그램을 만들려면  
  
1.  MFC 응용 프로그램 프로젝트를 만듭니다.  
  
     **파일** 메뉴에서 **새로 만들기**를 선택한 다음 **프로젝트**를 클릭합니다.  **Visual C\+\+** 폴더에서 **MFC 응용 프로그램**을 선택합니다.  
  
     **이름** 상자에 `MFC02`를 입력하고 **솔루션** 설정을 **솔루션에 추가**로 변경합니다.  **확인**을 클릭합니다.  
  
     **MFC 응용 프로그램 마법사**에서 기본값을 모두 적용한 다음 **마침**을 클릭합니다.  이렇게 하면 다중 문서 인터페이스가 포함된 MFC 응용 프로그램이 작성됩니다.  
  
2.  CLR\(공용 언어 런타임\)을 지원하도록 프로젝트를 구성합니다.  
  
     **솔루션 탐색기**에서 `MFC01` 프로젝트 노드를 마우스 오른쪽 단추로 클릭한 다음 상황에 맞는 메뉴에서 **속성**을 선택합니다.  **속성 페이지** 대화 상자가 나타납니다.  
  
     **구성 속성** 아래에서 **일반**을 선택합니다.  **프로젝트 기본값** 선택에서 **공용 언어 런타임 지원**을 **공용 언어 런타임 지원\(\/clr\)**으로 설정합니다.  
  
     **구성 속성**에서 **C\/C\+\+**를 확장하고 **일반** 노드를 클릭합니다.  **디버깅 정보 형식**을 **프로그램 데이터베이스\(\/Zi\)**로 설정합니다.  
  
     **코드 생성** 노드를 클릭합니다.  **최소 다시 빌드 사용**을 **아니요\(\/Gm\-\)**로 설정합니다.  또한 **기본 런타임 검사**를 **기본값**으로 설정합니다.  
  
     **확인**을 클릭하여 변경 내용을 적용합니다.  
  
3.  stdafx.h에서 다음 줄을 추가합니다.  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
4.  .NET 컨트롤에 대한 참조를 추가합니다.  
  
     **솔루션 탐색기**에서 `MFC02` 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **추가**, **참조**를 선택합니다.  **속성 페이지**에서 **새 참조 추가**를 클릭하고 **프로젝트** 탭 아래에서 WindowsFormsControlLibrary1을 선택한 다음 **확인**을 클릭합니다.  이렇게 하면 프로그램이 컴파일되도록 [\/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션의 형태로 참조가 추가되고 프로그램이 실행되도록 WindowsFormsControlLibrary1.dll이 `MFC02` 프로젝트 디렉터리에 복사됩니다.  
  
5.  stdafx.h에서 다음 줄을 찾습니다.  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     위에서 찾은 줄 위에 다음 코드를 추가합니다.  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  [CWinFormsView](../mfc/reference/cwinformsview-class.md)에서 상속되도록 뷰 클래스를 수정합니다.  
  
     MFC02View.h에서 다음 코드와 같이 [CView](../mfc/reference/cview-class.md)를 [CWinFormsView](../mfc/reference/cwinformsview-class.md)로 바꿉니다.  
  
    ```  
    class CMFC02View : public CWinFormsView  
    {  
    };  
    ```  
  
     MDI 응용 프로그램에 다른 뷰를 더 추가하려면 만들려는 각 뷰에 대해 [CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md)을 호출해야 합니다.  
  
7.  MFC02View.cpp 파일을 수정하여 IMPLEMENT\_DYNCREATE 매크로 및 메시지 맵에서 CView를 CWinFormsView로 변경하고 기존의 빈 생성자를 아래에 나와 있는 것과 같은 생성자로 바꿉니다.  
  
    ```  
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)  
  
    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)   
    {  
    }  
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)  
    //leave existing body as is  
    END_MESSAGE_MAP()  
    ```  
  
8.  프로젝트를 빌드하고 실행합니다.  
  
     **솔루션 탐색기**에서 MFC02를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **디버그** 메뉴에서 **디버깅하지 않고 시작**을 클릭합니다.  
  
## 참고 항목  
 [Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)