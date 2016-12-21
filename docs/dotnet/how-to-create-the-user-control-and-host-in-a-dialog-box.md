---
title: "방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC[C++], Windows Forms 컨트롤 호스팅"
  - "Windows Forms[C++], MFC 지원"
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서의 단계에서는 새로운 대화 상자 기반\([CDialog Class](../mfc/reference/cdialog-class.md)\) MFC\(Microsoft Foundation Classes\) 프로젝트를 만든다고 가정하지만, 기존의 MFC 대화 상자에도 Windows Forms 컨트롤에 대한 지원을 추가할 수 있습니다.  
  
### .NET 사용자 정의 컨트롤을 만들려면  
  
1.  `WindowsFormsControlLibrary1`이라는 Visual C\# Windows Forms 컨트롤 라이브러리 프로젝트를 만듭니다.  
  
     **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  **Visual C\#** 폴더에서 **Windows Forms 컨트롤 라이브러리**를 선택합니다.  
  
     **확인**을 클릭하여 프로젝트 이름인 `WindowsFormsControlLibrary1`을 그대로 적용합니다.  
  
     기본적으로 .NET 컨트롤의 이름은 `UserControl1`입니다.  
  
2.  `UserControl1`에 하위 컨트롤을 추가합니다.  
  
     **도구 상자**에서 **모든 Windows Forms** 목록을 엽니다.  **Button** 컨트롤을 `UserControl1` 디자인 화면에 끌어 놓습니다.  
  
     **TextBox** 컨트롤도 추가합니다.  
  
3.  **솔루션 탐색기**에서 **UserControl1.Designer.cs**를 두 번 클릭하여 편집할 파일을 엽니다.  TextBox 및 Button의 선언을 `private`에서 `public`으로 변경합니다.  
  
4.  프로젝트를 빌드합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
### MFC 호스트 응용 프로그램을 만들려면  
  
1.  MFC 응용 프로그램 프로젝트를 만듭니다.  
  
     **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  **Visual C\+\+** 폴더에서 **MFC 응용 프로그램**을 선택합니다.  
  
     **이름** 상자에 `MFC01`을 입력합니다.  솔루션 설정을 **솔루션에 추가**로 변경합니다.  **확인**을 클릭합니다.  
  
     **MFC 응용 프로그램 마법사**에서 응용 프로그램 종류로 **대화 상자 기반**을 선택합니다.  나머지 기본 설정을 그대로 적용하고 **마침**을 클릭합니다.  이렇게 하면 MFC 대화 상자가 있는 MFC 응용 프로그램이 만들어집니다.  
  
2.  MFC 대화 상자에 자리 표시자 컨트롤을 추가합니다.  
  
     **보기** 메뉴에서 **리소스 뷰**를 클릭합니다.  **리소스 뷰**에서 **대화 상자** 폴더를 확장하고 `IDD_MFC01_DIALOG`를 두 번 클릭합니다.  대화 상자 리소스가 **리소스 편집기**에 나타납니다.  
  
     **도구 상자**에서 **대화 상자 편집기** 목록을 엽니다.  **정적 텍스트** 컨트롤을 대화 상자 리소스에 끌어 놓습니다.  **정적 텍스트** 컨트롤은 .NET Windows Forms 컨트롤에 대한 자리 표시자로 사용됩니다.  Windows Forms 컨트롤의 크기에 맞도록 이 컨트롤의 크기를 조정합니다.  
  
     **속성** 창에서 **정적 텍스트** 컨트롤의 **ID**를 `IDC_CTRL1`로 변경하고 **TabStop** 속성을 **True**로 변경합니다.  
  
3.  CLR\(공용 언어 런타임\)을 지원하도록 프로젝트를 구성합니다.  
  
     **솔루션 탐색기**에서 MFC01 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
     **속성 페이지** 대화 상자에서 **구성 속성** 아래의 **일반**을 선택합니다.  **프로젝트 기본값** 선택에서 **공용 언어 런타임 지원**을 **공용 언어 런타임 지원\(\/clr\)**으로 설정합니다.  
  
     **구성 속성**에서 **C\/C\+\+**를 확장하고 **일반** 노드를 선택합니다.  **디버깅 정보 형식**을 **프로그램 데이터베이스\(\/Zi\)**로 설정합니다.  
  
     **코드 생성** 노드를 선택합니다.  **최소 다시 빌드 사용**을 **아니요\(\/Gm\-\)**로 설정합니다.  또한 **기본 런타임 검사**를 **기본값**으로 설정합니다.  
  
     **확인**을 클릭하여 변경 내용을 적용합니다.  
  
4.  .NET 컨트롤에 대한 참조를 추가합니다.  
  
     **솔루션 탐색기**에서 MFC01 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **추가**, **참조**를 클릭합니다.  **속성 페이지**에서 **새 참조 추가**를 클릭하고 **프로젝트** 탭 아래에서 **WindowsFormsControlLibrary1**을 선택한 다음 **확인**을 클릭합니다.  이렇게 하면 프로그램이 컴파일될 수 있도록 컴파일러 옵션 [\/FU](../build/reference/fu-name-forced-hash-using-file.md)의 형태로 참조가 추가됩니다.  또한 프로그램이 실행될 수 있도록 \\MFC01\\ 프로젝트 폴더에 WindowsFormsControlLibrary1.dll의 복사본이 배치됩니다.  
  
5.  Stdafx.h에서 다음 줄을 찾습니다.  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     위에서 찾은 줄 위에 다음 줄을 추가합니다.  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  관리되는 컨트롤을 만들기 위한 코드를 추가합니다.  
  
     먼저 관리되는 컨트롤을 선언합니다.  MFC01Dlg.h에서 대화 상자 클래스의 선언으로 이동하여 다음과 같이 Protected 범위에서 사용자 정의 컨트롤에 대한 데이터 멤버를 추가합니다.  
  
    ```  
    class CMFC01Dlg : public CDialog  
    {  
       // ...  
       // Data member for the .NET User Control:  
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;  
    ```  
  
     그런 다음 관리되는 컨트롤에 대한 구현을 제공합니다.  MFC01Dlg.cpp에서 동일한 파일에 있는 `CAboutDlg::DoDataExchange`가 아닌 MFC 응용 프로그램 마법사를 통해 생성된 `CMFC01Dlg::DoDataExchange`의 대화 상자 재정의로 이동합니다. 여기에 관리되는 컨트롤을 만들기 위한 다음 코드를 추가하고 이를 정적 자리 표시자 IDC\_CTRL1과 연결합니다.  
  
    ```  
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
    {  
       CDialog::DoDataExchange(pDX);  
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);  
    }  
    ```  
  
7.  프로젝트를 빌드하고 실행합니다.  
  
     **솔루션 탐색기**에서 **MFC01**을 마우스 오른쪽 단추로 클릭한 후 **시작 프로젝트로 설정**을 클릭합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **디버그** 메뉴에서 **디버깅하지 않고 시작**을 클릭합니다.  MFC 대화 상자에서 Windows Forms 컨트롤이 표시되어야 합니다.  
  
## 참고 항목  
 [MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)