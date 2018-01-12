---
title: "MFC의 사용자 정의 컨트롤을 형성 하는 Windows를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 59b4d974a6b25b896067bce0042d9a5ff9221cc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC에서 Windows Form 사용자 정의 컨트롤 사용
MFC Windows Forms 지원 클래스를 사용 하 여 Windows Forms 컨트롤 MFC 응용 프로그램 내에서 ActiveX 컨트롤 뷰 또는 MFC 대화 상자 내에서 호스트할 수 있습니다. 또한 Windows Forms 폼을 MFC 대화 상자로 호스팅할 수 있습니다.  
  
 다음 섹션에서는 설명 하는 방법:  
  
-   MFC 대화 상자에서 Windows Forms 컨트롤을 호스트 합니다.  
  
-   Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스트 합니다.  
  
-   MFC 대화 상자도 Windows Forms 폼을 호스팅하십시오.  
  
> [!NOTE]
>  MFC에 동적으로 연결 되는 프로젝트에만 작동 하는 MFC Windows Forms 통합 (프로젝트의 AFXDLL 정의 되어 있는 경우).  
  
> [!NOTE]
>  MFC Windows Forms 인터페이스 (mfcmifc80.dll) DLL의 전용 (수정 된) 복사본을 사용 하 여 응용 프로그램을 빌드할 때 사용자 고유의 공급 업체 키로 Microsoft 키를 대체 하지 않는 한 GAC에 설치 되지 것입니다. 어셈블리 서명에 대 한 자세한 내용은 참조 하십시오. [어셈블리를 사용한 프로그래밍](/dotnet/framework/app-domains/programming-with-assemblies) 및 [강력한 이름 어셈블리 (어셈블리 서명) (C + + /cli CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)합니다.  
  
 Windows Forms를 사용 하는 샘플 응용 프로그램에 대 한 참조 [BirthdayPicker 샘플: Windows Forms를 사용 하 여.NET Framework 리소스에서는](http://msdn.microsoft.com/en-us/ac932aed-5502-4667-be29-709bca435317), [계산기 샘플: Windows Forms Pocket 계산기](http://msdn.microsoft.com/en-us/2283b516-3b7e-45f2-80c4-fdcfb366ce25), 및 [ Scribble 샘플: MDI 그리기 응용 프로그램](http://msdn.microsoft.com/en-us/f025da3e-659b-4222-b991-554a1b8b2358)합니다.  
  
 MFC와 함께 사용 되는 Windows Forms를 보여 주는 샘플 응용 프로그램을 참조 하십시오. [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.  
  
 Windows Forms을 사용 하 여 MFC 응용 프로그램에 응용 프로그램과 함께 mfcmifc90.dll를 재배포 해야 합니다. 자세한 내용은 참조 [MFC 라이브러리 재배포](../ide/redistributing-the-mfc-library.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
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
  
 [CommandHandler](../atl/commandhandler.md)  
  
 [DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)  
  
 [UICheckState](../mfc/reference/uicheckstate-enumeration.md)  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Forms](/dotnet/framework/winforms/index)  
  
 [Windows Forms 컨트롤](/dotnet/framework/winforms/controls/index)  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)   
 [폼 보기](../mfc/form-views-mfc.md)