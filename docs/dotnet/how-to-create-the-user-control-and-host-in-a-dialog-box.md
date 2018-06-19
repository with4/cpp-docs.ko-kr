---
title: '방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 20472a80b35318fa4c6d34221a61345de9e40f9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136355"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기
이 문서의 단계를 만들고 있는 대화 상자 기반 가정 ([CDialog 클래스](../mfc/reference/cdialog-class.md)) Microsoft Foundation 클래스 (MFC) 프로젝트에 있지만 추가할 수 있습니다도 Windows Forms 컨트롤에 대 한 지원을 기존 MFC 대화 상자에 있습니다.  
  
### <a name="to-create-the-net-user-control"></a>.NET 사용자 컨트롤을 만들려면  
  
1.  라는 이름의 Visual C# Windows Forms 컨트롤 라이브러리 프로젝트 `WindowsFormsControlLibrary1`합니다.  
  
     **파일** 메뉴에서 **새로 만들기** 를 클릭한 다음 **프로젝트**를 클릭합니다. 에 **Visual C#** 폴더를 **Windows Forms 컨트롤 라이브러리**합니다.  
  
     수락 된 `WindowsFormsControlLibrary1` 프로젝트 이름을 클릭 하 여 **확인**합니다.  
  
     기본적으로.NET 컨트롤의 이름은 됩니다 `UserControl1`합니다.  
  
2.  자식 컨트롤을 추가할 `UserControl1`합니다.  
  
     에 **도구 상자**열고는 **모든 Windows Forms** 목록입니다. 끌어서는 **단추** 컨트롤을 `UserControl1` 디자인 화면입니다.  
  
     추가적으로 **TextBox** 제어 합니다.  
  
3.  **솔루션 탐색기**를 두 번 클릭 **UserControl1.Designer.cs** 를 편집 하기 위해 엽니다. 텍스트 상자 및 단추에서의 선언을 변경 `private` 를 `public`합니다.  
  
4.  프로젝트를 빌드합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면  
  
1.  MFC 응용 프로그램 프로젝트를 만듭니다.  
  
     **파일** 메뉴에서 **새로 만들기** 를 클릭한 다음 **프로젝트**를 클릭합니다. 에 **Visual c + +** 폴더를 **MFC 응용 프로그램**합니다.  
  
     **이름** 상자에 `MFC01`을 입력합니다. 솔루션 설정을 변경 **솔루션에 추가**합니다. **확인**을 클릭합니다.  
  
     에 **MFC 응용 프로그램 마법사**, 응용 프로그램 종류에 대 한 선택 **대화 상자 기반**합니다. 나머지 기본 설정을 적용 하 고 클릭 **마침**합니다. MFC 대화 상자에 있는 MFC 응용 프로그램을 만듭니다.  
  
2.  MFC 대화 상자에 자리 표시자 컨트롤을 추가 합니다.  
  
     에 **보기** 메뉴를 클릭 하 여 **리소스 뷰**합니다. **리소스 뷰**를 확장 하 고는 **대화** 폴더를 두 번 클릭 `IDD_MFC01_DIALOG`합니다. 에 표시 된 대화 상자 리소스 **리소스 편집기**합니다.  
  
     에 **도구 상자**열고는 **대화 상자 편집기** 목록입니다. 끌어서는 **정적 텍스트** 대화 상자 리소스를 제어 합니다. **정적 텍스트** 컨트롤.NET Windows Forms 컨트롤에 대 한 자리 표시자 역할을 수행 합니다. Windows Forms 컨트롤의 대략적인 크기를 조정 합니다.  
  
     **속성** 창에서 변경 된 **ID** 의 **정적 텍스트** 컨트롤을 `IDC_CTRL1` 변경는 **TabStop** 속성을 **True**합니다.  
  
3.  공용 언어 런타임 (CLR) 지원에 대 한 프로젝트를 구성 합니다.  
  
     **솔루션 탐색기**m f c 01 프로젝트 노드를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.  
  
     에 **속성 페이지** 대화 상자의 **구성 속성**선택, **일반**합니다. 에 **프로젝트 기본값** 섹션에서 설정 **공용 언어 런타임 지원** 를 **공용 언어 런타임 지원 (/ clr)** 합니다.  
  
     아래 **구성 속성**를 확장 하 고 **C/c + +** 선택 하 고는 **일반** 노드. 설정 **디버깅 정보 형식** 를 **프로그램 데이터베이스 (/Zi)** 합니다.  
  
     선택 된 **코드 생성** 노드. 설정 **최소 다시 빌드를 사용 하도록 설정** 를 **아니요 (/ Gm-)** 합니다. 또한 설정 **기본 런타임 검사** 를 **기본**합니다.  
  
     클릭 **확인** 변경 내용을 적용 합니다.  
  
4.  .NET 컨트롤에 대 한 참조를 추가 합니다.  
  
     **솔루션 탐색기**, m f c 01 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 클릭 **추가**, **참조**합니다. 에 **속성 페이지**, 클릭 **새 참조 추가**선택, **WindowsFormsControlLibrary1** (아래는 **프로젝트** 탭)를 클릭 하 고 **확인**합니다. 따라서 형식으로에 대 한 참조를 추가 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션을 프로그램 컴파일됩니다. 또한 프로그램이 실행 되 고 있도록 \MFC01\ 프로젝트 폴더의 WindowsFormsControlLibrary1.dll 사본을 저장 합니다.  
  
5.  Stdafx.h에서이 줄을 찾습니다.  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     그 위에 다음이 줄을 추가 합니다.  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  관리 되는 컨트롤을 만드는 코드를 추가 합니다.  
  
     첫째, 관리 되는 컨트롤을 선언 합니다. MFC01Dlg.h에서 대화 상자 클래스의 선언으로 이동 하 고 다음과 같이 보호 된 범위에서 사용자 정의 컨트롤에 대 한 데이터 멤버를 추가 합니다.  
  
    ```  
    class CMFC01Dlg : public CDialog  
    {  
       // ...  
       // Data member for the .NET User Control:  
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;  
    ```  
  
     다음으로 관리 되는 컨트롤에 대 한 구현을 제공 합니다. MFC01Dlg.cpp에서 대화 상자에서 재정의할 `CMFC01Dlg::DoDataExchange` MFC 응용 프로그램 마법사에서 생성 된 (하지 `CAboutDlg::DoDataExchange`, 같은 파일에), 관리 되는 컨트롤을 만들고 IDC_CTRL1 정적 자리 표시자와 연결 하려면 다음 코드를 추가 합니다.  
  
    ```  
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
    {  
       CDialog::DoDataExchange(pDX);  
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);  
    }  
    ```  
  
7.  프로젝트를 빌드하고 실행합니다.  
  
     **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **m f c 01** 클릭 하 고 **시작 프로젝트로 설정**합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     에 **디버그** 메뉴를 클릭 하 여 **디버깅 하지 않고 시작**합니다. MFC 대화 상자에는 Windows Forms 컨트롤에서 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)