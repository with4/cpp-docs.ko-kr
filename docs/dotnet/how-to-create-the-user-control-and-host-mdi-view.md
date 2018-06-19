---
title: '방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 449f0026cd2d7603ceb190cc747138189313974f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136485"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기
다음 단계에는.NET Framework 사용자 정의 컨트롤을 만들고, 컨트롤 클래스 라이브러리 (특히, Windows 컨트롤 라이브러리 프로젝트의 경우)에서 사용자 정의 컨트롤을 작성 한 다음 프로젝트를 어셈블리로 컴파일합니다 방법을 보여 줍니다. 컨트롤에서 파생 된 클래스를 사용 하 여 MFC 응용 프로그램에서 사용 될 수 [CView 클래스](../mfc/reference/cview-class.md) 및 [CWinFormsView 클래스](../mfc/reference/cwinformsview-class.md)합니다.  
  
 Windows Forms 사용자 정의 컨트롤 만들기 및 컨트롤 클래스 라이브러리를 제작 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 합성 컨트롤 제작](/dotnet/framework/winforms/controls/how-to-author-composite-controls)합니다.  
  
> [!NOTE]
>  경우에 따라 Windows Forms 컨트롤을 제 3 자 그리드 컨트롤 수 동작 하지 안정적으로 MFC 응용 프로그램에서 호스팅되는 경우. 권장된 해결 방법은 MFC 응용 프로그램에 Windows Forms 사용자 정의 컨트롤을 배치 하 고 사용자 정의 컨트롤 안에 있는 제 3 자 그리드 컨트롤을 배치 하는 것입니다.  
  
 이 절차의 절차에 따라 WindowsFormsControlLibrary1, 라는 Windows Forms 컨트롤 라이브러리 프로젝트를 만들었다고 가정 [하는 방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)합니다.  
  
### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면  
  
1.  MFC 응용 프로그램 프로젝트를 만듭니다.  
  
     에 **파일** 메뉴 선택 **새로**, 클릭 하 고 **프로젝트**합니다. 에 **Visual c + +** 폴더를 **MFC 응용 프로그램**합니다.  
  
     에 **이름** 상자에 입력 `MFC02` 변경 하 고는 **솔루션** 설정을 **솔루션에 추가**합니다. **확인**을 클릭합니다.  
  
     에 **MFC 응용 프로그램 마법사**, 모든 기본값을 적용 하 고 클릭 **마침**합니다. 이렇게 하면 다중 문서 인터페이스 MFC 응용 프로그램이 만들어집니다.  
  
2.  공용 언어 런타임 (CLR) 지원에 대 한 프로젝트를 구성 합니다.  
  
     **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 `MFC01` 프로젝트 노드를 선택한 **속성** 상황에 맞는 메뉴입니다. **속성 페이지** 대화 상자가 나타납니다.  
  
     아래 **구성 속성**선택, **일반**합니다. 아래는 **프로젝트 기본값** 섹션에서 설정 **공용 언어 런타임 지원** 를 **공용 언어 런타임 지원 (/ clr)** 합니다.  
  
     아래 **구성 속성**를 확장 하 고 **C/c + +** 클릭는 **일반** 노드. 설정 **디버깅 정보 형식** 를 **프로그램 데이터베이스 (/Zi)** 합니다.  
  
     클릭는 **코드 생성** 노드. 설정 **최소 다시 빌드를 사용 하도록 설정** 를 **아니요 (/ Gm-)** 합니다. 또한 설정 **기본 런타임 검사** 를 **기본**합니다.  
  
     클릭 **확인** 변경 내용을 적용 하려면.  
  
3.  Stdafx.h에서 다음 줄을 추가 합니다.  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
4.  .NET 컨트롤에 대 한 참조를 추가 합니다.  
  
     **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 `MFC02` 프로젝트 노드를 선택 **추가**, **참조**합니다. 에 **속성 페이지**, 클릭 **새 참조 추가**, WindowsFormsControlLibrary1 선택 (아래는 **프로젝트** 탭)를 클릭 하 고 **확인** . 따라서 형식으로에 대 한 참조를 추가 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션을 프로그램 컴파일됩니다; WindowsFormsControlLibrary1.dll에도 복사는 `MFC02` 프로그램이 실행 되 고 디렉터리를 프로젝트입니다.  
  
5.  Stdafx.h에서이 줄을 찾습니다.  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     위에 다음이 줄을 추가 합니다.  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  뷰 클래스에서 상속 하도록 수정 [CWinFormsView](../mfc/reference/cwinformsview-class.md)합니다.  
  
     MFC02View.h, 대체 [CView](../mfc/reference/cview-class.md) 와 [CWinFormsView](../mfc/reference/cwinformsview-class.md) 코드가 다음과 같이 나타나도록 합니다.  
  
    ```  
    class CMFC02View : public CWinFormsView  
    {  
    };  
    ```  
  
     호출 해야 다른 보기를 MDI 응용 프로그램에 추가할 것을 원할 경우 [CWinApp::AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) 만들면 각 보기에 대 한 합니다.  
  
7.  아래에 표시 된 생성자와 함께 기존 빈 생성자를 바꾸고 IMPLEMENT_DYNCREATE 매크로 및 메시지 맵에 CWinFormsView CView 변경 MFC02View.cpp 파일을 수정 합니다.  
  
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
  
     **솔루션 탐색기**m f c 02를 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트로 설정**합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     에 **디버그** 메뉴를 클릭 하 여 **디버깅 하지 않고 시작**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)