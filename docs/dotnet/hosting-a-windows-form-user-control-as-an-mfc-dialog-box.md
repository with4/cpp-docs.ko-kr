---
title: "사용자 정의 컨트롤을 MFC 대화 상자로 형성 Windows 호스팅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7ad1d800619eb84a470dbc5e472e9191d13e8796
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅
템플릿 클래스를 제공 하는 MFC [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) Windows Forms 사용자 정의 컨트롤을 호스팅할 수 있습니다 (<xref:System.Windows.Forms.UserControl>) 모달 또는 모덜리스 MFC 대화 상자에서 합니다. `CWinFormsDialog`MFC 클래스에서 파생 된 [CDialog](../mfc/reference/cdialog-class.md)이므로 modal 또는 모덜리스 대화 상자를 시작할 수 있습니다.  
  
 프로세스는 `CWinFormsDialog` 사용자 컨트롤을 호스트 하는 데 사용 하는에 설명 된 유사 [MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)합니다. 그러나 `CWinFormsDialog` 초기화 및 직접 프로그래밍할 수 하지 않아도 되도록 사용자 정의 컨트롤의 호스팅 관리 합니다.  
  
 MFC와 함께 사용 되는 Windows Forms를 보여 주는 샘플 응용 프로그램을 참조 하십시오. [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.  
  
### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면  
  
1.  MFC 응용 프로그램 프로젝트를 만듭니다.  
  
     에 **파일** 메뉴 선택 **새로**, 클릭 하 고 **프로젝트**합니다. 에 **Visual c + +** 폴더를 **MFC 응용 프로그램**합니다.  
  
     에 **이름** 상자에 입력 `MFC03` 솔루션 설정을 변경 하 고 **솔루션에 추가**합니다. 클릭 **확인**합니다.  
  
     에 **MFC 응용 프로그램 마법사**, 모든 기본값을 적용 하 고 클릭 **마침**합니다. 이렇게 하면 다중 문서 인터페이스 MFC 응용 프로그램이 만들어집니다.  
  
2.  프로젝트를 구성 합니다.  
  
     **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **MFC03** 프로젝트 노드를 마우스 선택 **속성**합니다. **속성 페이지** 대화 상자가 나타납니다.  
  
     에 **속성 페이지** 대화 상자는 **구성 속성** 트리 컨트롤 **일반**, 그런 다음는 **프로젝트 기본값**섹션에서 설정 **공용 언어 런타임 지원** 를 **공용 언어 런타임 지원 (/ clr)**합니다. **확인**을 클릭합니다.  
  
3.  .NET 컨트롤에 대 한 참조를 추가 합니다.  
  
     **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **MFC03** 프로젝트 노드를 선택 하 고 **추가**, **참조**합니다. 에 **속성 페이지**, 클릭 **새 참조 추가**, WindowsControlLibrary1 선택 (아래는 **프로젝트** 탭)를 클릭 하 고 **확인**합니다. 따라서 형식으로에 대 한 참조를 추가 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션을 프로그램 컴파일됩니다; WindowsControlLibrary1.dll에도 복사는 `MFC03` 프로그램이 실행 되 고 디렉터리를 프로젝트입니다.  
  
4.  추가 `#include <afxwinforms.h>` 기존 끝에서 stdafx.h로 `#include` 문.  
  
5.  해당 하위 클래스의 새 클래스를 추가 `CDialog`합니다.  
  
     프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 해당 서브 클래스는 MFC 클래스 (호출된 CHostForWinForm) 추가 `CDialog`합니다. 대화 상자 리소스를 불필요 한 이후 리소스 ID를 삭제할 수 있습니다 (리소스 보기를 선택, 대화 폴더를 확장 및 않으므로 리소스를 삭제 합니다.  그런 다음 ID에 대 한 참조에서에서 제거 코드 합니다.).  
  
6.  대체 `CDialog` CHostForWinForm.h 및 CHostForWinForm.cpp 파일 `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`합니다.  
  
7.  DoModal CHostForWinForm 클래스에서 호출 합니다.  
  
     MFC03.cpp, 추가 `#include "HostForWinForm.h"`합니다.  
  
     CMFC03App::InitInstance의 정의에 return 문이 하기 전에 다음을 추가 합니다.  
  
     `CHostForWinForm m_HostForWinForm;`  
  
     `m_HostForWinForm.DoModal();`  
  
8.  프로젝트를 빌드하고 실행합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     에 **디버그** 메뉴를 클릭 하 여 **디버깅 하지 않고 시작**합니다.  
  
     다음 MFC 응용 프로그램에서 Windows Forms에 컨트롤의 상태를 모니터링 하는 코드를 추가 합니다.  
  
9. OnInitDialog에 대 한 처리기를 추가 합니다.  
  
     표시는 **속성** 창 (F4). **클래스 뷰**, CHostForWinForm를 선택 합니다. 에 **속성** 창 선택 재정의 및 왼쪽 열에서 OnInitDialog에 대 한 행을 클릭 및 선택 \< 추가 > 합니다. 이 CHostForWinForm.h에 다음 줄을 추가합니다.  
  
    ```  
    virtual BOOL OnInitDialog();  
    ```  
  
10. OnInitDialog (CHostForWinForm.cpp)에서 다음과 같이 정의 합니다.  
  
    ```  
    BOOL CHostForWinForm::OnInitDialog() {  
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();  
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);  
       return TRUE;  
    }  
    ```  
  
11. 다음 OnButton1 처리기를 추가 합니다. CHostForWinForm.h에서 CHostForWinForm 클래스의 공용 섹션에 다음 줄 추가:  
  
    ```  
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );  
  
    BEGIN_DELEGATE_MAP( CHostForWinForm )  
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );  
    END_DELEGATE_MAP()  
    ```  
  
     CHostForWinForm.cpp에서이 정의 추가 합니다.  
  
    ```  
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )   
    {  
       System::Windows::Forms::MessageBox::Show("test");  
    }  
    ```  
  
12. 프로젝트를 빌드하고 실행합니다. Windows Form에 있는 단추를 클릭 하면 MFC 응용 프로그램의 코드가 실행 됩니다.  
  
     다음 Windows Form에 텍스트 상자에 값을 MFC 코드에서 표시 하는 코드를 추가 합니다.  
  
13. CHostForWinForm.h에서 CHostForWinForm 클래스의 공용 섹션에 다음 선언을 추가 합니다.  
  
    ```  
    CString m_sEditBoxOnWinForm;  
    ```  
  
14. DoDataExchange CHostForWinForm.cpp의 정의에 함수의 끝에 다음 세 줄을 추가 합니다.  
  
    ```  
    if (pDX->m_bSaveAndValidate)  
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);  
    else  
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);  
    ```  
  
15. OnButton1 CHostForWinForm.cpp의 정의에 함수의 끝에 다음 세 줄을 추가 합니다.  
  
    ```  
    this->UpdateData(TRUE);  
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);  
    System::Windows::Forms::MessageBox::Show(z);  
    ```  
  
16. 프로젝트를 빌드하고 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)