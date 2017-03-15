---
title: "Example: Implementing a Property Page | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "속성 페이지, 구현"
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Example: Implementing a Property Page
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

속성 페이지의 속성을 표시 \(및 변경할 수 있습니다\)을 작성 하는 방법을 보여 주는이 예제는 [문서 클래스](../mfc/document-classes.md) 인터페이스.  이 인터페이스에서 Visual Studio 문서 노출 [Common Environment Object Model Examples](../Topic/Common%20Environment%20Object%20Model%20Examples.md) \(만들게 속성 페이지는 올바른 인터페이스 지원으로 조작 되는 개체의 출처 신경쓰지 않습니다 있지만\).  
  
 예제를 기반으로  [ATLPages 샘플](../top/visual-cpp-samples.md).  
  
 이 예제를 완료 하려면 다음을 수행할 수 있습니다.  
  
-   [ATL 속성 페이지 클래스를 추가 합니다.](#vcconusing_the_atl_object_wizard) ATL 속성 페이지 마법사 및 클래스 추가 대화 상자를 사용 합니다.  
  
-   [대화 상자 리소스 편집](#vcconediting_the_dialog_resource) 흥미로운 속성에 대해 새 컨트롤을 추가 하는  **문서** 인터페이스.  
  
-   [메시지 처리기 추가](#vcconadding_message_handlers) 변경 사용자가 알림을 속성 페이지 사이트를 유지 합니다.  
  
-   일부 추가 `#import` 문 및 형식 정의에  [정리 작업](#vcconhousekeeping) 섹션.  
  
-   [재정의 IPropertyPageImpl::SetObjects](#vcconoverriding_ipropertypageimpl_setobjects) 속성 페이지에 전달 되는 개체의 유효성을 검사 합니다.  
  
-   [재정의 IPropertyPageImpl::Activate](#vcconoverriding_ipropertypageimpl_activate) 속성 페이지 인터페이스를 초기화할 수 있습니다.  
  
-   [재정의 IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply) 최신 속성 값으로 개체를 업데이트할 수 있습니다.  
  
-   [속성 페이지를 표시 합니다.](#vccontesting_the_property_page) 간단한 도우미 개체를 생성 합니다.  
  
-   [매크로 만들기](#vcconcreating_a_macro) 속성 페이지를 테스트 합니다.  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> ATL 속성 페이지 클래스를 추가합니다.  
 먼저 새 ATL 프로젝트의 DLL 서버를 만드는 `ATLPages7`.  지금 사용 하는  [ATL 속성 페이지 마법사](../atl/reference/atl-property-page-wizard.md) 속성 페이지를 생성 합니다.  속성 페이지를 제공는  **약식 이름** 의  **DocProperties** 다음 전환의  **문자열** 페이지 속성 페이지 관련 항목 아래의 표와 같이 설정 합니다.  
  
|항목|값|  
|--------|-------|  
|제목|TextDocument|  
|문서 문자열|VCUE TextDocument 속성|  
|도움말 파일|*\<blank\>*|  
  
 호출할 때 마법사의이 페이지에서 설정 된 값을 속성 페이지 컨테이너에 반환 됩니다  **IPropertyPage::GetPageInfo**.  어떤 컨테이너를 다릅니다 있지만 일반적으로 사용자에 게 페이지를 식별할 수 사용 될 문자열을 발생 합니다.  제목은 대개 페이지 위의 탭에 나타납니다 및 \(표준 속성 프레임이 문자열이 전혀 사용 하지 않지만\) 문서 문자열은 상태 표시줄이 나 도구 설명에 표시 될 수 있습니다.  
  
> [!NOTE]
>  여기서 설정한 문자열 마법사가 프로젝트에서 문자열 리소스로 저장 됩니다.  페이지에 대 한 코드를 생성 한 후이 정보를 변경 하는 경우 리소스 편집기를 사용 하 여 이러한 문자열을 쉽게 편집할 수 있습니다.  
  
 클릭  **확인** 속성 페이지가 생성 되도록 합니다.  
  
##  <a name="vcconediting_the_dialog_resource"></a> 대화 상자 리소스를 편집합니다.  
 생성 된 속성 페이지에는 페이지를 나타내는 대화 상자 리소스에는 몇 가지 컨트롤을 추가 해야 합니다.  편집 상자, 정적 텍스트 컨트롤 및 확인란을 추가 하 고 Id 아래와 같이 설정 합니다.  
  
 ![대화 상자 리소스 편집](../atl/media/ppgresourcelabeled.png "PPGResourceLabeled")  
  
 문서의 파일 이름과 읽기 전용 상태를 표시 하려면 이러한 컨트롤을 사용할 것입니다.  
  
> [!NOTE]
>  대화 상자 리소스 프레임 또는 명령 단추 뿐만 아니라 예상 된 탭된 형태를가지고 있지.  호출 하 여 만든 것과 같이 속성 페이지 프레임이 기능 제공 하는  [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437).  
  
##  <a name="vcconadding_message_handlers"></a> 메시지 처리기를 추가합니다.  
 컨트롤 컨트롤의 값이 변경 될 때 페이지의 변경 상태를 업데이트 하는 메시지 처리기를 추가할 수 있습니다.  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/CPP/example-implementing-a-property-page_1.h)]  
  
 이 코드를 호출 하 여 편집 컨트롤 또는 확인란에 변경한 내용을 응답  [IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md), 페이지에서 변경 된 페이지 사이트를 알립니다.  페이지 사이트 활성화 또는 비활성화 하 여 응답 합니다 일반적으로  **적용** 속성 페이지 프레임 단추.  
  
> [!NOTE]
>  자신의 속성 페이지에서 변경 되지 않았는지 확인 하는 속성을 업데이트 하지 않도록 수 있도록 정확 하 게 어떤 속성 사용자가 변경 된 추적 해야 합니다.  이 예제 코드는 원래 속성 값을 추적 하 고 변경 내용을 적용할 때 UI의 현재 값으로 비교를 구현 합니다.  
  
##  <a name="vcconhousekeeping"></a> 정리 작업  
 이제 몇 가지 추가 `#import` DocProperties.h 문을 컴파일러에서 인식 하는  **문서** 인터페이스:  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/CPP/example-implementing-a-property-page_2.h)]  
  
 참조 해야 합니다의 `IPropertyPageImpl` 기본 클래스입니다. 다음 추가 `typedef` 에 있는  **CDocProperties** 클래스:  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/CPP/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> Ipropertypageimpl::setobjects를 재정의합니다.  
 첫 번째 `IPropertyPageImpl` 재정의 해야 할 메서드는  [SetObjects](../Topic/IPropertyPageImpl::SetObjects.md).  전달 되는 단일 개체만 지원 하는지 확인 하는 코드를 추가 합니다 여기는  **문서** 기대 하는 인터페이스:  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/CPP/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  사용자 개체의 파일 이름을 설정할 수 있기 때문에 하나의 개체만이 페이지에 대 한 지원에 적합\-하나의 파일을 존재할 수 있습니다.  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> Ipropertypageimpl::activate를 재정의합니다.  
 다음 단계 페이지가 처음 만들어질 때 내부 개체의 속성 값을 속성 페이지를 초기화 하는 것.  
  
 이 경우 페이지의 사용자가 변경 내용을 적용할 때 비교에 대 한 초기 속성 값 사용할 수 없으므로 클래스에 다음 멤버를 추가 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/CPP/example-implementing-a-property-page_5.h)]  
  
 기본 클래스 구현에서  [활성화](../Topic/IPropertyPageImpl::Activate.md) 메서드는이 메서드를 재정의 하 고 직접 초기화 후 기본 클래스를 호출을 추가할 수 있도록 대화 상자 및 해당 컨트롤을 작성 합니다:  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/CPP/example-implementing-a-property-page_6.h)]  
  
 이 코드의 COM 메서드를 사용 하는  **문서** 원하는 등록 정보를 가져오기 위한 인터페이스입니다.  그런 다음 제공 되는 Win32 API 래퍼를 사용  [CDialogImpl](../atl/reference/cdialogimpl-class.md) 및 해당 기본 클래스 속성 값을 사용자에 게 표시 합니다.  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> Ipropertypageimpl::apply를 재정의합니다.  
 사용자 개체에 변경 내용을 적용 하려는 경우 속성 페이지 사이트 호출 되는  [적용](../Topic/IPropertyPageImpl::Apply.md) 메서드.  이 코드를 반대로 수행 합니다.  **활성화** \-반면  **활성화** 개체에서 값을 받고 컨트롤 속성 페이지에 들어갑니다  **적용** 컨트롤의 속성 페이지에서 매개 변수 및 해당 개체를 푸시합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/CPP/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  검사에 대 한  [m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md) 이 구현 부분에 경우 개체의 불필요 한 업데이트를 방지 하는 초기 검사는  **적용** 두 번 이상 호출 됩니다.  또한 각 변경 메서드가 호출 될 수 있도록 속성 값에 대 한 검사는의  **문서**.  
  
> [!NOTE]
>  **문서** 노출  **FullName** 은 읽기 전용 속성입니다.  속성 페이지의 변경에 따라 문서의 파일 이름을 업데이트 하려면 사용 해야는  **저장** 파일을 다른 이름으로 저장 하는 메서드.  따라서 속성 페이지에서 코드 자체를 제한 하지 않아도 가져오거나 속성을 설정 합니다.  
  
##  <a name="vccontesting_the_property_page"></a> 속성 페이지를 표시합니다.  
 이 페이지를 표시 하려면 간단한 도우미 개체를 만들 필요 합니다.  도우미 개체를 단순화 하는 메서드를 제공 합니다의  **OleCreatePropertyFrame** 단일 페이지를 표시 하는 API는 단일 개체에 연결 합니다.  이 도우미는 Visual Basic 사용할 수 있도록 디자인 됩니다.  
  
 사용 하는  [클래스 추가 대화 상자](../ide/add-class-dialog-box.md) 및  [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md) 새 클래스를 생성 하 고 사용 `Helper` 짧은 이름으로.  작성 후 아래 표와 같이 메서드를 추가 합니다.  
  
|항목|값|  
|--------|-------|  
|메서드 이름|`ShowPage`|  
|매개 변수|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 `bstrCaption` 매개 변수는 캡션 대화 상자 제목으로 표시 됩니다.  `bstrID` 매개 변수는 CLSID 또는 ProgID 속성 페이지를 표시 하는 string입니다.  `pUnk` 매개 변수 수는 `IUnknown` 포인터가 개체 속성이 속성 페이지에서 구성 됩니다.  
  
 아래와 같이 메서드를 구현 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/CPP/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a> 매크로 만들기  
 프로젝트를 빌드한 후에 속성 페이지와 도우미 개체를 만들고 Visual Studio 개발 환경에서 실행 하는 간단한 매크로 사용 하 여 테스트할 수 있습니다.  도우미는이 매크로 만듭니다 개체를 호출 하 고 해당  **ShowPage** 의 Progid를 사용 하 여 메서드는  **DocProperties** 속성 페이지와  **IUnknown** 포인터 Visual Studio 편집기에서 현재 활성 문서의.  이 매크로에 필요한 코드는 다음과 같습니다.  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
  
Public Module AtlPages  
  
    Public Sub Test()  
        Dim Helper  
        Helper = CreateObject("ATLPages7.Helper.1")  
  
        On Error Resume Next  
        Helper.ShowPage( _  
            ActiveDocument.Name, _  
            "ATLPages7Lib.DocumentProperties.1", _  
            DTE.ActiveDocument _  
            )  
    End Sub  
  
End Module  
```  
  
 이 매크로 실행 하면 파일 이름 및 텍스트를 현재 문서의 읽기 전용 상태를 표시 합니다. 속성 페이지가 표시 됩니다.  문서의 읽기 전용 상태에는 개발 환경에서 문서를 작성할 수만 반영 됩니다. 디스크에 있는 파일의 읽기 전용 특성이 영향을 주지 않습니다.  
  
## 참고 항목  
 [속성 페이지](../atl/atl-com-property-pages.md)   
 [ATLPages 샘플](../top/visual-cpp-samples.md)