---
title: "MFC에서 Windows Form 사용자 정의 컨트롤 사용 | Microsoft Docs"
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
  - "MFC [c + +], Windows Forms 지원"
  - "상호 운용성 [c + +] MFC의 Windows Forms"
  - "상호 운용성 [c + +] MFC"
  - "MFC의 Windows Forms interop [c + +]"
  - "MFC interop [c + +]"
  - "Windows Forms [c + +] MFC 지원"
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC에서 Windows Form 사용자 정의 컨트롤 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC Windows Forms 지원 클래스를 사용 하 여 Windows Forms 컨트롤 MFC 응용 프로그램 내에서 ActiveX 컨트롤 MFC 대화 상자 또는 뷰 내에서 호스트할 수 있습니다. 또한 MFC 대화 상자는 Windows Forms 폼을 호스팅할 수 있습니다.  
  
 다음 섹션에서는 설명 하는 방법:  
  
-   MFC 대화 상자에서 Windows Forms 컨트롤을 호스트 합니다.  
  
-   MFC 뷰로으로 Windows Forms 사용자 정의 컨트롤을 호스팅하십시오.  
  
-   MFC 대화 상자도 Windows Forms 폼을 호스팅하십시오.  
  
> [!NOTE]
>  MFC에 동적으로 연결 되는 프로젝트에만 작동 하는 MFC Windows Forms 통합 (프로젝트의 AFXDLL 정의 되어 있는 경우).  
  
> [!NOTE]
>  MFC Windows Forms 인터페이스 DLL (mfcmifc80.dll)의 전용 (수정 된) 복사본을 사용 하 여 응용 프로그램을 빌드할 때 사용자 고유의 공급 업체 키로 Microsoft 키를 대체 하지 않는 한 GAC에 설치 되지 것입니다. 어셈블리 서명에 대 한 자세한 내용은 참조 하십시오. [어셈블리를 사용한 프로그래밍](../Topic/Programming%20with%20Assemblies.md) 및 [강력한 이름 어셈블리 (어셈블리 서명) (C + + /cli CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)합니다.  
  
 Windows Forms를 사용 하는 샘플 응용 프로그램에 대 한 참조 [BirthdayPicker 샘플: Windows Forms를 사용 하 여.NET Framework 리소스는 방법을 보여 줍니다](http://msdn.microsoft.com/ko-kr/ac932aed-5502-4667-be29-709bca435317), [계산기 샘플: Windows Forms Pocket 계산기](http://msdn.microsoft.com/ko-kr/2283b516-3b7e-45f2-80c4-fdcfb366ce25), 및 [Scribble 샘플: MDI 그리기 응용 프로그램](http://msdn.microsoft.com/ko-kr/f025da3e-659b-4222-b991-554a1b8b2358)합니다.  
  
 MFC와 함께 사용 되는 Windows Forms를 보여 주는 샘플 응용 프로그램을 참조 하십시오. [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.  
  
 Windows Forms을 사용 하 여 MFC 응용 프로그램 mfcmifc90.dll 응용 프로그램과 함께 재배포 해야 합니다. 자세한 내용은 참조 [MFC 라이브러리 재배포](../ide/redistributing-the-mfc-library.md)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)  
  
 [Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)  
  
 [Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)  
  
## <a name="reference"></a>참조  
 [CWinFormsControl 클래스](../mfc/reference/cwinformscontrol-class.md)  
  
 [CWinFormsDialog 클래스](../mfc/reference/cwinformsdialog-class.md)  
  
 [CWinFormsView 클래스](../mfc/reference/cwinformsview-class.md)  
  
 [ICommandSource 인터페이스](../mfc/reference/icommandsource-interface.md)  
  
 [ICommandTarget 인터페이스](../mfc/reference/icommandtarget-interface.md)  
  
 [ICommandUI 인터페이스](../mfc/reference/icommandui-interface.md)  
  
 [IView 인터페이스](../mfc/reference/iview-interface.md)  
  
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)  
  
 [CommandUIHandler](../Topic/CommandUIHandler%20Delegate.md)  
  
 [DDX_ManagedControl](../Topic/DDX_ManagedControl.md)  
  
 [UICheckState](../Topic/UICheckState%20Enumeration.md)  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Forms](../Topic/Windows%20Forms.md)  
  
 [Windows Forms 컨트롤](../Topic/Windows%20Forms%20Controls.md)  
  
 [ASP.NET 사용자 정의 컨트롤](../Topic/ASP.NET%20User%20Controls.md)  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)   
 [폼 뷰](../mfc/form-views-mfc.md)