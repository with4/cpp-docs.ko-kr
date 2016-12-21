---
title: "Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "Windows Forms 컨트롤 호스팅[C++]"
  - "MFC[C++], Windows Forms 지원"
  - "Windows Forms[C++], MFC 대화 상자로 호스팅"
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC에서는 모달 또는 모덜리스 MFC 대화 상자에 Windows Forms 사용자 정의 컨트롤\(<xref:System.Windows.Forms.UserControl>\)을 호스팅할 수 있도록 템플릿 클래스 [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md)를 제공합니다.  `CWinFormsDialog`는 MFC 클래스 [CDialog](../mfc/reference/cdialog-class.md)에서 파생되므로 대화 상자를 모달 또는 모덜리스로 시작할 수 있습니다.  
  
 `CWinFormsDialog`에서 사용자 정의 컨트롤을 호스팅하기 위해 사용하는 과정은 [MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)에서 설명하는 과정과 비슷합니다.  그러나 `CWinFormsDialog`는 사용자 정의 컨트롤의 초기화 및 호스팅 과정을 자동으로 관리하므로 이를 직접 프로그래밍할 필요가 없습니다.  
  
 MFC와 함께 사용 하는 Windows Forms을 보여 주는 샘플 응용 프로그램은 [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)을 참조하십시오.  
  
### MFC 호스트 응용 프로그램을 만들려면  
  
1.  MFC 응용 프로그램 프로젝트를 만듭니다.  
  
     **파일** 메뉴에서 **새로 만들기**를 선택한 다음 **프로젝트**를 클릭합니다.  **Visual C\+\+** 폴더에서 **MFC 응용 프로그램**을 선택합니다.  
  
     **이름** 상자에 `MFC03`을 입력하고 솔루션 설정을 **솔루션에 추가**로 변경합니다. **확인**을 클릭합니다.  
  
     **MFC 응용 프로그램 마법사**에서 기본값을 모두 적용한 다음 **마침**을 클릭합니다.  이렇게 하면 다중 문서 인터페이스가 포함된 MFC 응용 프로그램이 작성됩니다.  
  
2.  프로젝트를 구성합니다.  
  
     **솔루션 탐색기**에서 **MFC03** 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  **속성 페이지** 대화 상자가 나타납니다.  
  
     **속성 페이지** 대화 상자의 **구성 속성** 트리 컨트롤에서 **일반**을 선택한 다음 **프로젝트 기본값** 섹션에서 **공용 언어 런타임 지원**을 **공용 언어 런타임 지원\(\/clr\)**으로 설정합니다.  **확인**을 클릭합니다.  
  
3.  .NET 컨트롤에 대한 참조를 추가합니다.  
  
     **솔루션 탐색기**에서 **MFC03** 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **추가**, **참조**를 선택합니다.  **속성 페이지**에서 **새 참조 추가**를 클릭하고 **프로젝트** 탭 아래에서 WindowsControlLibrary1을 선택한 다음 **확인**을 클릭합니다.  이렇게 하면 프로그램이 컴파일되도록 [\/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션의 형태로 참조가 추가되고 프로그램이 실행되도록 WindowsControlLibrary1.dll이 `MFC03` 프로젝트 디렉터리에 복사됩니다.  
  
4.  stdafx.h에서 기존 `#include` 문 끝에 `#include <afxwinforms.h>`를 추가합니다.  
  
5.  `CDialog`를 서브클래싱하는 새 클래스를 추가합니다.  
  
     프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 `CDialog`를 서브클래싱하는 CHostForWinForm이라는 MFC 클래스를 추가합니다.  대화 상자 리소스는 필요하지 않으므로 리소스 ID를 삭제할 수 있습니다. 즉, 리소스 뷰를 선택하고 대화 상자 폴더를 확장한 다음 IDD\_HOSTFORWINFORM 리소스를 삭제하고  코드에서 ID에 대한 모든 참조를 제거합니다.  
  
6.  CHostForWinForm.h 및 CHostForWinForm.cpp 파일에서 `CDialog`를 `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`로 바꿉니다.  
  
7.  CHostForWinForm 클래스에서 DoModal을 호출합니다.  
  
     MFC03.cpp에 `#include "HostForWinForm.h"`를 추가합니다.  
  
     CMFC03App::InitInstance의 정의에서 return 문 앞에 다음 코드를 추가합니다.  
  
     `CHostForWinForm m_HostForWinForm;`  
  
     `m_HostForWinForm.DoModal();`  
  
8.  프로젝트를 빌드하고 실행합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **디버그** 메뉴에서 **디버깅하지 않고 시작**을 클릭합니다.  
  
     다음으로는 MFC 응용 프로그램에서 Windows Forms의 컨트롤 상태를 모니터링하는 코드를 추가합니다.  
  
9. OnInitDialog에 대한 처리기를 추가합니다.  
  
     F4 키를 눌러 **속성** 창을 표시합니다.  **클래스 뷰**에서 CHostForWinForm을 선택합니다.  **속성** 창에서 재정의를 선택하고 OnInitDialog가 있는 행에서 왼쪽 열을 클릭한 다음 \< 추가 \>를 선택합니다.  그러면 CHostForWinForm.h에 다음 줄이 추가됩니다.  
  
    ```  
    virtual BOOL OnInitDialog();  
    ```  
  
10. 다음과 같이 CHostForWinForm.cpp에서 OnInitDialog를 정의합니다.  
  
    ```  
    BOOL CHostForWinForm::OnInitDialog() {  
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();  
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);  
       return TRUE;  
    }  
    ```  
  
11. 그런 다음 OnButton1 처리기를 추가합니다.  CHostForWinForm.h에서 CHostForWinForm 클래스의 public 섹션에 다음 줄을 추가합니다.  
  
    ```  
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );  
  
    BEGIN_DELEGATE_MAP( CHostForWinForm )  
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );  
    END_DELEGATE_MAP()  
    ```  
  
     CHostForWinForm.cpp에 다음 정의를 추가합니다.  
  
    ```  
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )   
    {  
       System::Windows::Forms::MessageBox::Show("test");  
    }  
    ```  
  
12. 프로젝트를 빌드하고 실행합니다.  Windows Form에 있는 단추를 클릭하면 MFC 응용 프로그램의 코드가 실행됩니다.  
  
     다음으로는 MFC 코드에서 텍스트 상자의 값을 Windows Form에 표시하는 코드를 추가합니다.  
  
13. CHostForWinForm.h에서 CHostForWinForm 클래스의 public 섹션에 다음 선언을 추가합니다.  
  
    ```  
    CString m_sEditBoxOnWinForm;  
    ```  
  
14. CHostForWinForm.cpp의 DoDataExchange 정의에서 함수의 끝에 다음 세 줄을 추가합니다.  
  
    ```  
    if (pDX->m_bSaveAndValidate)  
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);  
    else  
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);  
    ```  
  
15. CHostForWinForm.cpp의 OnButton1 정의에서 함수의 끝에 다음 세 줄을 추가합니다.  
  
    ```  
    this->UpdateData(TRUE);  
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);  
    System::Windows::Forms::MessageBox::Show(z);  
    ```  
  
16. 프로젝트를 빌드하고 실행합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)