---
title: "다중 페이지 문서 | Microsoft Docs"
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
- pagination [MFC]
- overriding [MFC], View class functions for printing
- OnPrepareDC method [MFC]
- CPrintInfo structure [MFC], multipage documents
- OnEndPrinting method [MFC]
- protocols [MFC], printing protocol
- document pages vs. printer pages [MFC]
- printer mode [MFC]
- printing [MFC], multipage documents
- printers [MFC], printer mode
- documents [MFC], printing
- OnPreparePrinting method [MFC]
- OnPrint method [MFC]
- DoPreparePrinting method and pagination [MFC]
- OnDraw method [MFC], printing
- pagination [MFC], printing multipage documents
- printing [MFC], protocol
- pages [MFC], printing
- OnBeginPrinting method [MFC]
- multipage documents [MFC]
- printing [MFC], pagination
- documents [MFC], paginating
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43bc9bbe4653e34c37ae46439baa1e649d6d8042
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multipage-documents"></a>다중 페이지 문서
이 문서는 Windows 인쇄 프로토콜을 설명 하 고 여러 페이지를 포함 하는 문서를 인쇄 하는 방법에 설명 합니다. 문서는 다음 항목을 다룹니다.  
  
-   [인쇄 프로토콜](#_core_the_printing_protocol)  
  
-   [뷰 클래스 함수 재정의](#_core_overriding_view_class_functions)  
  
-   [페이지 매김](#_core_pagination)  
  
-   [문서 페이지 및 프린터 페이지](#_core_printer_pages_vs.._document_pages)  
  
-   [인쇄 시간 페이지 매김](#_core_print.2d.time_pagination)  
  
##  <a name="_core_the_printing_protocol"></a>인쇄 프로토콜  
 다중 페이지 문서를 인쇄 하려면 프레임 워크 및 보기는 다음과 같은 방식에서 상호 작용 합니다. 프레임 워크가 표시 하는 먼저는 **인쇄** 대화 상자에서 프린터 및 호출에 대 한 장치 컨텍스트를 만듭니다.는 [StartDoc](../mfc/reference/cdc-class.md#startdoc) 의 멤버 함수는 [CDC](../mfc/reference/cdc-class.md) 개체입니다. 그런 다음 문서의 각 페이지에 대 한 프레임 워크에서 호출 된 [StartPage](../mfc/reference/cdc-class.md#startpage) 의 멤버 함수는 `CDC` 개체, 페이지 및 호출을 인쇄 하려면 view 개체를 지시는 [EndPage](../mfc/reference/cdc-class.md#endpage) 멤버 함수입니다. 뷰를 호출 하는 특정 페이지를 시작 하기 전에 프린터 모드를 변경 해야 하는 경우 [ResetDC](../mfc/reference/cdc-class.md#resetdc), 업데이트는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 새 프린터 모드 정보가 포함 된 구조입니다. 프레임 워크를 호출 하는 전체 문서를 인쇄는 [EndDoc](../mfc/reference/cdc-class.md#enddoc) 멤버 함수입니다.  
  
##  <a name="_core_overriding_view_class_functions"></a>뷰 클래스 함수 재정의  
 [CView](../mfc/reference/cview-class.md) 클래스 인쇄 하는 동안 프레임 워크에서 호출 되는 몇 가지 멤버 함수를 정의 합니다. 뷰 클래스에서 이러한 함수를 재정의 하 여 간 연결 프레임 워크의 인쇄 논리 및 뷰 클래스의 인쇄 논리를 제공 합니다. 다음 표에서 이러한 멤버 함수를 나열합니다.  
  
### <a name="cviews-overridable-functions-for-printing"></a>인쇄용 CView의 재정의 가능 함수  
  
|name|재정의 대 한 설명|  
|----------|---------------------------|  
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|문서의 길이 특히 인쇄 대화 상자에서 값을 삽입 하려면|  
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|글꼴 또는 기타 GDI 리소스 할당|  
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|지정된 된 페이지에 대 한 장치 컨텍스트의 특성을 조정 하거나 인쇄 시간 페이지 매김|  
|[OnPrint](../mfc/reference/cview-class.md#onprint)|지정된 된 페이지를 인쇄 하려면|  
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|GDI 리소스 할당을 취소 하려면|  
  
 도 다른 함수에서 인쇄 관련 처리를 수행할 수 있지만 이러한 함수는 인쇄 프로세스를 구동 하는 것입니다.  
  
 다음 그림에서는 인쇄 프로세스에 관련 된 단계와 위치를 보여 줍니다 각 `CView`의 멤버 함수는 호출을 인쇄 합니다. 이 문서의 나머지 부분에서는 대부분의 이러한 단계를 자세히 설명합니다. 인쇄 프로세스의 추가 파트 문서에 설명 된 [GDI 리소스 할당](../mfc/allocating-gdi-resources.md)합니다.  
  
 ![루프 프로세스 인쇄](../mfc/media/vc37c71.gif "vc37c71")  
인쇄 루프  
  
##  <a name="_core_pagination"></a>페이지 매김  
 프레임 워크에서 인쇄 작업에 대 한 정보를 저장 한 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 구조입니다. 에 있는 값의 여러 `CPrintInfo` 페이지 매김과 관련; 이러한 값은 다음 표에 나와 있는 것 처럼 액세스할 수 있습니다.  
  
### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo에 저장 된 페이지 번호 정보  
  
|멤버 변수 또는<br /><br /> 함수 이름|페이지 번호 참조|  
|-----------------------------------------------|----------------------------|  
|`GetMinPage`/`SetMinPage`|문서의 첫 번째 페이지|  
|`GetMaxPage`/`SetMaxPage`|문서의 마지막 페이지|  
|`GetFromPage`|인쇄할 첫 번째 페이지|  
|`GetToPage`|마지막 페이지를 인쇄|  
|`m_nCurPage`|현재 인쇄 중인 페이지|  
  
 페이지 번호는 1부터 시작 즉, 첫 번째 페이지는 지정 된 1, 0이 아닌 합니다. 이러한 오류 코드 및의 다른 멤버에 대 한 자세한 내용은 [CPrintInfo](../mfc/reference/cprintinfo-structure.md), 참조는 *MFC 참조*합니다.  
  
 인쇄 프로세스를 시작할 때 프레임 워크에서 호출 보기의 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 에 대 한 포인터를 전달 하는 멤버 함수는 `CPrintInfo` 구조입니다. 응용 프로그램 마법사의 구현을 제공 `OnPreparePrinting` 호출 하는 [DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting)의 다른 멤버 함수 `CView`합니다. `DoPreparePrinting`프린터 장치 컨텍스트를 만듭니다. 인쇄 대화 상자를 표시 하는 함수가입니다.  
  
 이 시점에서 응용 프로그램은 문서에 있는 페이지 수를 알지 못합니다. 기본값 1 및 0xFFFF를 사용 하 여 문서의 첫 번째 및 마지막 페이지 번호에 대 한 합니다. 문서에는 페이지 수를 알고 있는 경우 재정의 `OnPreparePrinting` 호출 [에 대 한 SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage)는 `CPrintInfo` 를 보내기 전에 구조체 `DoPreparePrinting`합니다. 이 문서의 길이 지정할 수 있습니다.  
  
 `DoPreparePrinting`그런 다음 인쇄 대화 상자를 표시합니다. 반환 시는 `CPrintInfo` 구조는 사용자가 지정한 값을 포함 합니다. 선택한 일정 범위의 페이지를 인쇄 하려는 경우 자신이 시작과 끝 페이지 번호 인쇄 대화 상자에서 지정할 수 있습니다. 사용 하 여 이러한 값을 검색 하는 프레임 워크는 `GetFromPage` 및 `GetToPage` 의 기능 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)합니다. 프레임 워크를 호출 하는 사용자 페이지 범위를 지정 하지 않으면 `GetMinPage` 및 `GetMaxPage` 전체 문서를 인쇄 하려면 반환 값을 사용 합니다.  
  
 각 문서를 인쇄할 페이지에 대 한 프레임 워크 뷰 클래스에 두 개의 멤버 함수를 호출 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 및 [OnPrint](../mfc/reference/cview-class.md#onprint), 각 함수에 두 개의 매개 변수가 전달:에 대 한 포인터는 [ CDC](../mfc/reference/cdc-class.md) 개체 및에 대 한 포인터는 `CPrintInfo` 구조입니다. 프레임 워크 호출 될 때마다 `OnPrepareDC` 및 `OnPrint`에서 다른 값을 전달 하기는 `m_nCurPage` 의 멤버는 `CPrintInfo` 구조입니다. 이러한 방식으로 프레임 워크 인쇄 페이지 보기 알려 줍니다.  
  
 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 멤버 함수는 화면 표시에도 사용 됩니다. 그리기를 수행 하기 전에 장치 컨텍스트를 조정을 합니다. `OnPrepareDC`인쇄에 비슷한 역할을 제공 합니다.는 몇 가지 차이 있지만:, 첫 번째는 `CDC` 개체 화면 장치 컨텍스트 및 초를 하는 대신 프린터 장치 컨텍스트를 나타냅니다는 `CPrintInfo` 개체는 두 번째 매개 변수로 전달 됩니다. (이 매개 변수는 **NULL** 때 `OnPrepareDC` 화면 표시에 대해 호출 됩니다.) 재정의 `OnPrepareDC` 인쇄 페이지에 따라 장치 컨텍스트를 조정 합니다. 예를 들어 뷰포트 원점과 문서의 해당 부분을 가져옵니다 인쇄 되도록 하려면 클립 영역을 이동할 수 있습니다.  
  
 [OnPrint](../mfc/reference/cview-class.md#onprint) 멤버 함수는 페이지의 실제 인쇄를 수행 합니다. 문서 [기본 인쇄 수행 방법](../mfc/how-default-printing-is-done.md) 프레임 워크에서 호출 방법을 보여 줍니다. [OnDraw](../mfc/reference/cview-class.md#ondraw) 인쇄를 수행 하는 프린터 장치 컨텍스트를 사용 합니다. 프레임 워크 호출 보다 정확 하 게 `OnPrint` 와 `CPrintInfo` 구조 및 장치 컨텍스트 및 `OnPrint` 장치 컨텍스트를 전달 `OnDraw`합니다. 재정의 `OnPrint` 를 인쇄 하는 동안에 및 화면 디스플레이 대해 수행 되어야 하는 렌더링을 수행 합니다. 예를 들어, 머리글 또는 바닥글을 인쇄 하려면 (문서를 참조 [머리글 및 바닥글](../mfc/headers-and-footers.md) 자세한 정보에 대 한). 그런 다음 호출 `OnDraw` 의 재정의에서 `OnPrint` 모두 화면 표시에 공통적인 렌더링 및 인쇄를 수행 합니다.  
  
 팩트는 `OnDraw` 렌더링은 둘 다 화면 표시 및 인쇄 응용 프로그램 WYSIWYG 임을 의미에 대해: "What you see is 결과가." 그러나 WYSIWYG 응용 프로그램은 작성 하지 가정 합니다. 예를 들어 텍스트 편집기 인쇄에 굵은 글꼴을 사용 하지만 화면에 굵은 텍스트를 나타내는 제어 코드를 표시 합니다. 이러한 상황을 사용 하 여 `OnDraw` 화면 표시에 엄격 하 게 합니다. 재정의 하는 경우 `OnPrint`, 대체에 대 한 호출 `OnDraw` 별도 그리기 기능을 호출 합니다. 해당 함수는 화면에 표시 하지 않는 특성을 사용 하 여 용지에 표시 되는 문서를 그립니다.  
  
##  <a name="_core_printer_pages_vs.._document_pages"></a>프린터 페이지 vs입니다. 문서 페이지  
 페이지 번호를 참조 하는 경우 페이지의 프린터의 개념 및 페이지의 문서의 개념을 구분 하기 위해 하는 경우가 있습니다. 프린터의 관점에서 한 페이지에는 하나의 용지의 합니다. 그러나 하나의 용지의 문서 한 페이지 반드시와 같지 않습니다. 예를 들어 있는 시트 접을 수에 않을 회보 인쇄 하는 경우 한 용지의 나란히 문서의 첫 번째 및 마지막 페이지 포함 될 수 있습니다. 마찬가지로, 스프레드시트, 인쇄 하는 경우 문서가 구성 되지 않습니다 페이지 전혀 합니다. 대신, 하나의 용지의 1-6-10 열 20 행을 포함할 수 있습니다.  
  
 모든 페이지 번호는 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 구조 프린터 페이지를 참조 하십시오. 프레임 워크를 호출 하 여 `OnPrepareDC` 및 `OnPrint` 프린터는 통과 문서의 각 시트에 대해 한 번씩입니다. 재정의 하는 경우는 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 문서 길이 지정 하려면 함수를 프린터 페이지를 사용 해야 합니다. 한 일 대응 하는 경우 (즉, 한 프린터 페이지는 한 문서 페이지 equals) 간단 합니다. 반면에 문서 페이지와 프린터 페이지 일치 하지 않는 직접 하는 경우 서로 변환 해야 합니다. 예를 들어 스프레드시트를 인쇄 하는 것이 좋습니다. 재정의 하는 경우 `OnPreparePrinting`, 용지 시트 수 해야 하며 전체 스프레드시트를 인쇄 하 고 호출할 때 해당 값을 사용 하 여 다음을 계산 해야는 `SetMaxPage` 의 멤버 함수 `CPrintInfo`합니다. 마찬가지로, 재정의 하는 경우 `OnPrepareDC`를 변환 해야 `m_nCurPage` 특정 시트에 표시 되 고 다음 뷰포트 origin을 적절 하 게 조정 하는 행과 열 범위에 있습니다.  
  
##  <a name="_core_print.2d.time_pagination"></a>인쇄 시간 페이지 매김  
 경우에 따라 뷰 클래스 모를 수 미리 기간 문서가 실제로 인쇄 될 때까지 합니다. 예를 들어, 응용 프로그램 WYSIWYG이 아니라고 가정 하므로 문서 길이 화면에 해당 하지 않습니다 인쇄할 때의 길이에.  
  
 재정의 하는 경우 문제가 발생 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 뷰 클래스에 대 한: 값을 전달할 수 없습니다는 `SetMaxPage` 의 함수는 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 의 길이 알 수 없으므로 구조는 문서입니다. 사용자가 인쇄 대화 상자를 사용 하 여 중지 하는 페이지 번호를 지정 하지 않으면 인쇄 루프를 중지 하는 경우 프레임 워크가 모릅니다. 인쇄 루프를 중지할 시기를 결정 하는 유일한 방법은 하는 문서를 인쇄 하 고 끝날 때 참조 됩니다. 뷰 클래스 끝에 도달할 때 프레임 워크를 다음 알립니다 인쇄 하는 동안 문서 끝에 대 한 확인 해야 합니다.  
  
 뷰 클래스의 의존 하는 프레임 워크 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 함수를 알려을 중지 합니다. 호출할 때마다 `OnPrepareDC`의 멤버를 확인 하는 프레임 워크는 `CPrintInfo` 라는 구조 `m_bContinuePrinting`합니다. 기본값은 **TRUE입니다.** 해으로 프레임 워크가 인쇄 루프를 계속 합니다. 로 설정 되어 있으면 **FALSE**, 프레임 워크 중지 합니다. 인쇄 때 페이지 번호 매기기를 수행 하려면 재정의 `OnPrepareDC` 문서 끝에 도달 하 고 설정 여부를 확인 하려면 `m_bContinuePrinting` 를 **FALSE** 할당 했을 때.  
  
 기본 구현은 `OnPrepareDC` 설정 `m_bContinuePrinting` 를 **FALSE** 현재 페이지 1 보다 큰 경우. 이 경우 문서 길이 지정 하지 않았습니다. 프레임 워크 가정 문서 길이 한 페이지로 것을 의미 합니다. 이 사용자의 기본 클래스 버전을 호출 하는 경우 주의 해야 `OnPrepareDC`합니다. 이라고 단정 하지 마십시오 `m_bContinuePrinting` 됩니다 **TRUE** 기본 클래스 버전을 호출한 후 합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [머리글 및 바닥글](../mfc/headers-and-footers.md)  
  
-   [GDI 리소스 할당](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>참고 항목  
 [인쇄](../mfc/printing.md)   
 [CView 클래스](../mfc/reference/cview-class.md)   
 [CDC 클래스](../mfc/reference/cdc-class.md)