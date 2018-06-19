---
title: 속성 페이지 (ATL) 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages, implementing
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 139bdd9076e99139f4da105b4bb2b375689efe15
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363715"
---
# <a name="example-implementing-a-property-page"></a>예: 속성 페이지 구현
속성을 표시 (및 변경할 수 있습니다) 하는 속성 페이지를 빌드하는 방법을 보여 주는이 예제는 [문서 클래스](../mfc/document-classes.md) 인터페이스입니다.  
  
 예제 기반는 [ATLPages 샘플](../visual-cpp-samples.md)합니다.  
  
 이 예제를 완료 하려면 다음을 수행 합니다.  
  
- [ATL 속성 페이지 클래스의 추가](#vcconusing_the_atl_object_wizard) 클래스 추가 대화 상자와 ATL 속성 페이지 마법사를 사용 하 여 합니다.  
  
- [대화 상자 리소스 편집](#vcconediting_the_dialog_resource) 의 중요 한 속성에 대 한 새 컨트롤을 추가 하 여는 **문서** 인터페이스입니다.  
  
- [메시지 처리기 추가](#vcconadding_message_handlers) 속성 페이지 사이트를 유지 하려면 사용자가 변경 되 면 알림을 합니다.  
  
-   일부 추가 `#import` 문과의 형식 정의 [Housekeeping](#vcconhousekeeping) 섹션.  
  
- [IPropertyPageImpl::SetObjects 재정의](#vcconoverriding_ipropertypageimpl_setobjects) 을 속성 페이지에 전달 되는 개체를 검사 합니다.  
  
- [IPropertyPageImpl::Activate 재정의](#vcconoverriding_ipropertypageimpl_activate) 속성 페이지의 인터페이스를 초기화 합니다.  
  
- [IPropertyPageImpl::Apply 재정의](#vcconoverride_ipropertypageimpl_apply) 최신 속성 값을 가진 개체를 업데이트 합니다.  
  
- [속성 페이지를 표시](#vccontesting_the_property_page) 간단한 도우미 개체를 만들어 합니다.  
  
- [매크로 만들](#vcconcreating_a_macro) 하는 속성 페이지를 테스트 합니다.  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> ATL 속성 페이지 클래스 추가  
 먼저 라고 하는 DLL 서버에 대 한 새 ATL 프로젝트를 만듭니다 `ATLPages7`합니다. 사용 하 여 이제는 [ATL 속성 페이지 마법사](../atl/reference/atl-property-page-wizard.md) 속성 페이지를 생성 하 합니다. 속성 페이지를 제공는 **약식 이름** 의 **DocProperties** 다음 전환 하는 **문자열** 아래 표에 나와 있는 것 처럼 속성 페이지의 관련 항목을 설정 하는 페이지입니다.  
  
|항목|값|  
|----------|-----------|  
|제목|TextDocument|  
|문서 문자열|VCUE TextDocument 속성|  
|도움말 파일|*\<빈 >*|  
  
 마법사의이 페이지에서 설정 값을 호출 하는 경우 속성 페이지 컨테이너에 반환 됩니다 **IPropertyPage::GetPageInfo**합니다. 컨테이너에 따라 달라 집니다 하지만 일반적으로 사용할 사용자에 게 해당 페이지를 알리는 후 문자열에 진행 합니다. 제목 일반적으로 페이지 위의 탭에 나타나고 문서 문자열 (설명이이 문자열을 전혀 사용 하지 않는) 하지만 상태 표시줄이 나 도구에 표시 될 수 있습니다.  
  
> [!NOTE]
>  여기에서 설정 하는 문자열은 마법사에서 프로젝트에 리소스 문자열으로 저장 됩니다. 페이지에 대 한 코드를 생성 한 후이 정보를 변경 해야 할 경우 리소스 편집기를 사용 하 여 이러한 문자열을 쉽게 편집할 수 있습니다.  
  
 클릭 **확인** 속성 페이지를 생성 하면 마법사가 있습니다.  
  
##  <a name="vcconediting_the_dialog_resource"></a> 대화 상자 리소스 편집  
 이제 속성 페이지가 생성 된 경우에 해당 페이지를 나타내는 대화 상자 리소스에 몇 가지 컨트롤을 추가 해야 합니다. 편집 상자, 정적 텍스트 컨트롤 및 확인란을 추가 하 고 아래와 같이 해당 Id를 설정 합니다.  
  
 ![대화 상자 리소스 편집](../atl/media/ppgresourcelabeled.gif "ppgresourcelabeled")  
  
 이러한 컨트롤은 문서 및 서버 인스턴스의 읽기 전용 상태의 파일 이름을 표시 하려면 사용 됩니다.  
  
> [!NOTE]
>  대화 상자 리소스에는 프레임이 나 명령 단추 아니며 예상 된 탭된 형태 사용 하지 않습니다. 이러한 기능을 호출 하 여 만든 것과 같은 속성 페이지 프레임 제공 [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437)합니다.  
  
##  <a name="vcconadding_message_handlers"></a> 메시지 처리기 추가  
 현재 위치에 있는 컨트롤과 컨트롤의 값이 변경 될 때 페이지의 변경 상태를 업데이트 하는 메시지 처리기를 추가할 수 있습니다.  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]  
  
 이 코드를 호출 하 여 편집 컨트롤 또는 확인란에 대 한 변경을 응답 [IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty), 페이지 변경 된 페이지 사이트에 게 알립니다. 페이지 사이트는 활성화 또는 비활성화 하 여 응답 하는 일반적으로 **적용** 속성 페이지 프레임에서 단추입니다.  
  
> [!NOTE]
>  사용자 고유의 속성 페이지에서 추적 하기 위해 정확 하 게 되는 속성 변경 된 사용자가 변경 되지 않은 속성을 업데이트 하지 않도록 할 수 있습니다. 이 예제에서는 원래 속성 값 및 추적 하는 변경 내용을 적용 하려면 UI의 현재 값과 비교 하 여 해당 코드를 구현 합니다.  
  
##  <a name="vcconhousekeeping"></a> 정리 작업  
 이제 몇 가지 추가 `#import` DocProperties.h 문을 컴파일러에 대 한 알 수 있도록는 **문서** 인터페이스:  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]  
  
 참조 해야는 `IPropertyPageImpl` 기본 클래스에 다음 추가; `typedef` 에 **CDocProperties** 클래스:  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> IPropertyPageImpl::SetObjects 재정의  
 첫 번째 `IPropertyPageImpl` 재정의 해야 하는 메서드는 [SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)합니다. 단일 개체를 전달 된를 지원 하는지 확인 하는 코드를 추가 여기는 **문서** 하는데 인터페이스:  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  이렇게 하면 사용자가 개체의 파일 이름을 설정 하도록 허용 하는 때문에이 페이지에 대 한 단일 개체만 지원 하-어느 한 위치에 파일이 하나만 있을 수 있습니다.  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> IPropertyPageImpl::Activate 재정의  
 다음 단계는 페이지를 처음 만들 때 기본 개체의 속성 값을 가진 속성 페이지를 초기화 하는 것입니다.  
  
 이 경우 것도 초기 속성 값 비교를 사용 하면 페이지의 사용자는 자신의 변경 내용을 적용 하므로 클래스에는 다음과 같은 멤버를 추가 해야:  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]  
  
 기본 클래스 구현을 [Activate](../atl/reference/ipropertypageimpl-class.md#activate) 메서드는이 메서드를 재정의 하 고 기본 클래스를 호출한 후 직접 초기화를 추가할 수 있도록 대화 상자 및 폼의 컨트롤을 만듭니다.  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]  
  
 이 코드의 COM 메서드를 사용 하 여는 **문서** 인터페이스를 원하는 속성을 가져옵니다. 제공 하는 Win32 API 래퍼를 사용 하 여 다음 [CDialogImpl](../atl/reference/cdialogimpl-class.md) 와 사용자에 게 속성 값을 표시 하려면 해당 기본 클래스입니다.  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> IPropertyPageImpl::Apply 재정의  
 사용자가 개체에 변경 내용을 적용 하려고 하면 속성 페이지 사이트를 호출 합니다는 [적용](../atl/reference/ipropertypageimpl-class.md#apply) 메서드. 여기에서의 코드 반대로 작업할 수 **Activate** -반면 **Activate** 는 개체의 값을 적용 하 고 해당 속성 페이지에 있는 컨트롤에 푸시되 **적용** 속성 페이지에 있는 컨트롤에서 값을 사용 하 고 개체에 밀어넣습니다.  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  에 대 한 확인 [m_bDirty](../atl/reference/ipropertypageimpl-class.md#m_bdirty) 이 구현은 맨 앞에 개체의 불필요 한 업데이트를 방지 하려면 초기에 검사 **적용** 두 번 이상 호출 됩니다. 각각의 변경 된 내용만 심한 메서드 호출에는 속성 값에 대 한 검사는 또한는 **문서**합니다.  
  
> [!NOTE]
> **문서** 노출 **FullName** 읽기 전용 속성으로. 속성 페이지에 대 한 변경 내용을 기반으로 문서의 파일 이름을 업데이트 하려면 사용 하 여 할는 **저장** 메서드를 다른 이름으로 파일을 저장 합니다. 따라서 속성 페이지의에서 코드를 제한할 필요가 없습니다 자체를 수집 또는 속성을 설정 합니다.  
  
##  <a name="vccontesting_the_property_page"></a> 속성 페이지 표시  
 이 페이지를 표시 하려면 간단한 도우미 개체를 만듭니다. 도우미 개체를 간소화 하는 메서드를 제공 합니다는 **OleCreatePropertyFrame** 단일 페이지를 표시 하기 위한 API 단일 개체에 연결 합니다. 이 도우미는 Visual Basic에서 사용할 수 있도록 디자인 됩니다.  
  
 사용 하 여는 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md) 및 [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md) 새 클래스를 생성 하 여 사용할 `Helper` 짧은 이름으로 합니다. 를 만든 후 아래 표에 나와 있는 것 처럼 메서드를 추가 합니다.  
  
|항목|값|  
|----------|-----------|  
|메서드 이름|`ShowPage`|  
|매개 변수|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 `bstrCaption` 매개 변수는 대화 상자의 제목으로 표시할 캡션입니다. `bstrID` 매개 변수는 CLSID 또는 ProgID 속성 페이지의 표시를 나타내는 문자열입니다. `pUnk` 매개 변수는 `IUnknown` 속성 페이지에서 구성할 속성이 있는 개체의 포인터입니다.  
  
 아래와 같이 메서드를 구현 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a> 매크로 만들기  
 작성 한 후 프로젝트를 만들고 Visual Studio 개발 환경에서 실행할 수 있는 간단한 매크로 사용 하 여 도우미 개체 및 속성 페이지를 테스트할 수 있습니다. 이 매크로 도우미 만들어집니다 개체를 호출 합니다. 해당 **페이지 표시** 의 ProgID를 사용 하 여 메서드는 **DocProperties** 속성 페이지 및 **IUnknown** 문서 포인터 Visual Studio 편집기에서 현재 활성 상태입니다. 이 매크로에 필요한 코드는 다음과 같습니다.  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
 
Public Module AtlPages  
 
    Public Sub Test()  
    Dim Helper  
    Helper = CreateObject("ATLPages7.Helper.1")  
 
    On Error Resume Next  
    Helper.ShowPage(_ 
    ActiveDocument.Name,
    _ 
 "ATLPages7Lib.DocumentProperties.1",
    _ 
    DTE.ActiveDocument _)  
    End Sub  
 
End Module  
```  
  
 이 매크로 실행 하면 파일 이름 및 현재 활성 텍스트 문서의 읽기 전용 상태를 나타내는 속성 페이지에 표시 됩니다. 문서는 읽기 전용 상태가 반영 되며 개발 환경에서 문서에 쓸 수 디스크에 파일의 읽기 전용 특성이 변경 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../atl/atl-com-property-pages.md)   
 [ATLPages 샘플](../visual-cpp-samples.md)

