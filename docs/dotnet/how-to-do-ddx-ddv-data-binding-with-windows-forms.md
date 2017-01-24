---
title: "방법: Windows Forms에서 DDX/DDV 데이터 바인딩 수행 | Microsoft Docs"
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
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Windows Forms에서 DDX/DDV 데이터 바인딩 수행
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[DDX\_ManagedControl](../Topic/DDX_ManagedControl.md)은 [CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md)을 호출하여 리소스 컨트롤 ID와 일치하는 컨트롤을 만듭니다.  마법사로 생성한 코드에서 `CWinFormsControl` 컨트롤에 대해 `DDX_ManagedControl`을 사용하는 경우 동일한 컨트롤에 대해 `CreateManagedControl`을 명시적으로 호출하지 말아야 합니다.  
  
 리소스 ID에서 컨트롤을 만들려면 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)에서 `DDX_ManagedControl`을 호출합니다.  데이터 교환의 경우 Windows Forms 컨트롤과 함께 DDX\/DDV 함수를 사용할 필요가 없습니다.  대신, 다음 예제에서와 같이 관리 코드의 속성에 액세스하는 코드를 대화 상자 또는 뷰 클래스의 `DoDataExchange` 메서드에 배치할 수 있습니다.  
  
 다음 예제에서는 네이티브 C\+\+ 문자열을 .NET 사용자 정의 컨트롤에 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 다음은 .NET 사용자 정의 컨트롤의 `NameText` 속성이 사용자 정의된 MFC 문자열 `m_str`의 DDX\/DDV 데이터 바인딩 예제입니다.  
  
 [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)에서 `CMyDlg::DoDataExchange`를 처음 호출할 때 컨트롤이 작성되므로 `m_UserControl`을 참조하는 모든 코드는 `DDX_ManagedControl` 호출 뒤에 와야 합니다.  
  
 [방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)에서 만든 MFC01 응용 프로그램에서 이 코드를 구현할 수 있습니다.  
  
 CMFC01Dlg 선언에 다음 코드를 배치합니다.  
  
```  
class CMFC01Dlg : public CDialog  
{  
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;  
   CString m_str;  
};  
```  
  
## 예제  
 CMFC01Dlg 구현에 다음 코드를 배치합니다.  
  
```  
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
{  
   CDialog::DoDataExchange(pDX);  
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);  
  
   if (pDX->m_bSaveAndValidate) {  
      m_str = m_MyControl->textBox1->Text;  
   } else  
   {  
      m_MyControl->textBox1->Text = gcnew System::String(m_str);  
   }  
}  
```  
  
## 예제  
 이제 OK 단추의 클릭을 처리하는 메서드를 추가합니다.  **리소스 뷰** 탭을 클릭합니다.  리소스 뷰에서 `IDD_MFC01_DIALOG`를 두 번 클릭합니다.  대화 상자 리소스가 리소스 편집기에 나타납니다.  그런 다음 OK 단추를 두 번 클릭합니다.  
  
 처리기를 다음과 같이 정의합니다.  
  
```  
void CMFC01Dlg::OnBnClickedOk()  
{  
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));  
   OnOK();  
}  
```  
  
## 예제  
 BOOL CMFC01Dlg::OnInitDialog\(\) 구현에 다음 줄을 추가합니다.  
  
```  
m_MyControl.GetControl()->textBox1->Text = "hello";  
```  
  
 이제 응용 프로그램을 빌드하여 실행할 수 있습니다.  응용 프로그램이 종료될 때 텍스트 상자에 있는 모든 텍스트가 팝업 메시지 상자에 표시됩니다.  
  
## 참고 항목  
 [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md)   
 [DDX\_ManagedControl](../Topic/DDX_ManagedControl.md)   
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)