---
title: "MFC ActiveX 컨트롤: ActiveX 컨트롤 그리기 | Microsoft Docs"
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
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2a2dc7b0cebbfaa6f6fe7dbe7dc69e5d4f80121
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 그리기
이 문서에서는 ActiveX 컨트롤 그리기 프로세스와 프로세스를 최적화하는 그리기 코드를 변경하는 방법을 설명합니다. (참조 [컨트롤 그리기 최적화](../mfc/optimizing-control-drawing.md) 이전에 선택한 GDI 개체를 복원 하 여 개별적으로 컨트롤 없이 그리기를 최적화 하는 방법은 대. 모든 컨트롤이 그려진 후 컨테이너에서 원래 개체를 자동으로 복원할 수 있습니다.  
  
 이 문서의 예제는 MFC ActiveX 컨트롤 마법사에서 기본 설정으로 만들어진 컨트롤에서 제공됩니다. MFC ActiveX 컨트롤 마법사를 사용 하 여 기본 컨트롤 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 문서 참조 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)합니다.  
  
 다음 항목을 설명합니다.  
  
-   [컨트롤과 그리기를 지원 하기 위해 ActiveX 컨트롤 마법사가 생성 한 코드를 그리기 위한 전체 프로세스](#_core_the_painting_process_of_an_activex_control)  
  
-   [그리기 프로세스를 최적화 하는 방법](#_core_optimizing_your_paint_code)  
  
-   [메타 파일을 사용 하 여 컨트롤을 그리는 방법](#_core_painting_your_control_using_metafiles)  
  
##  <a name="_core_the_painting_process_of_an_activex_control"></a>ActiveX 컨트롤의 그리기 프로세스  
 ActiveX 컨트롤이 처음 표시되거나 다시 그려지는 경우 해당 컨트롤은 MFC를 사용하여 개발된 다른 응용 프로그램과 유사한 그리기 프로세스를 따릅니다. 중요한 차이점 하나는 ActiveX 컨트롤이 활성 또는 비활성 상태가 될 수 있다는 점입니다.  
  
 활성 컨트롤은 자식 창에서 ActiveX 컨트롤 컨테이너에 표시됩니다. 다른 창과 마찬가지로 `WM_PAINT` 메시지가 수신될 때 직접 그려야 합니다. 컨트롤의 기본 클래스 [COleControl](../mfc/reference/colecontrol-class.md)에서이 메시지를 처리 합니다. 해당 `OnPaint` 함수입니다. 이 기본 구현은 컨트롤의 `OnDraw` 함수를 호출합니다.  
  
 비활성 컨트롤은 다르게 그려집니다. 컨트롤이 비활성화인 경우 해당 창은 표시되지 않거나 존재하지 않으므로 그리기 메시지를 받을 수 없습니다. 대신 컨트롤 컨테이너에서는 컨트롤의 `OnDraw` 함수를 직접 호출합니다. 이는 `OnPaint` 멤버 함수가 호출되지 않는 활성 컨트롤의 그리기 프로세스와 다릅니다.  
  
 이전 단락에서 설명한 것처럼 ActiveX 컨트롤을 업데이트하는 방법은 컨트롤의 상태에 따라 다릅니다. 그러나 두 경우 모두 프레임워크에서 `OnDraw` 멤버 함수를 호출하므로 이 멤버 함수에 그리기 코드 대부분을 추가합니다.  
  
 `OnDraw` 멤버 함수에서 컨트롤 그리기를 처리합니다. 컨트롤이 활성화되는 경우 컨트롤 컨테이너에서는 `OnDraw`를 호출하여 컨트롤 컨테이너의 장치 컨텍스트 및 컨트롤이 차지한 사각형 영역의 좌표를 전달합니다.  
  
 프레임워크에서 `OnDraw` 멤버 함수에 전달된 사각형에는 컨트롤이 차지한 영역이 포함되어 있습니다. 컨트롤이 활성화된 경우 왼쪽 위 모서리는 (0, 0)이고, 전달된 장치 컨텍스트는 컨트롤을 포함한 자식 창에 대한 것입니다. 컨트롤이 비활성화된 경우 왼쪽 위 좌표는 반드시 (0,0)이 아니고, 전달된 장치 컨텍스트는 컨트롤을 포함한 컨트롤 컨테이너에 대한 것입니다.  
  
> [!NOTE]
>  것이 중요 하에 수정 사항을 `OnDraw` 사각형의 왼쪽된 위 지점이 같은지에 종속 되지 않는 (0, 0)에 전달 된 사각형 내부 에서만 그려야 합니다 및 `OnDraw`합니다. 사각형의 영역을 넘어 그릴 경우 예기치 않은 결과가 발생할 수 있습니다.  
  
 아래와 같은 컨트롤 구현 파일(.CPP)에서 MFC ActiveX 컨트롤 마법사에 의해 제공되는 기본 구현은 사각형을 흰색 브러시로 색칠하고 타원을 현재 배경색으로 채웁니다.  
  
 [!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]  
  
> [!NOTE]
>  컨트롤을 그릴 때 수 정도 해서는 안 변수로 전달 되는 장치 컨텍스트의 상태에 대 한는 *pdc* 매개 변수는 `OnDraw` 함수입니다. 경우에 따라 장치 컨텍스트는 컨테이너 응용 프로그램에서 제공되며 반드시 기본 상태로 초기화되지 않습니다. 특히 펜, 브러시, 색, 글꼴 및 그리기 코드가 종속된 다른 리소스를 명시적으로 선택합니다.  
  
##  <a name="_core_optimizing_your_paint_code"></a>그리기 코드 최적화  
 컨트롤을 성공적으로 그린 후 다음 단계는 `OnDraw` 함수를 최적화하는 것입니다.  
  
 ActiveX 컨트롤 그리기의 기본 구현은 전체 컨트롤 영역을 그리는 것입니다. 이 작업은 간단한 컨트롤에 충분하지만 전체 컨트롤 대신 업데이트가 필요한 부분이 다시 그려질 경우에만 대부분의 컨트롤 다시 그리기는 더 빨라집니다.  
  
 `OnDraw` 함수는 다시 그려야 하는 컨트롤의 사각형 영역인 `rcInvalid`를 전달하여 최적화하는 쉬운 방법을 제공합니다. 그리기 프로세스의 속도를 높이려면 일반적으로 전체 컨트롤 영역보다 더 작은 이 영역을 사용합니다.  
  
##  <a name="_core_painting_your_control_using_metafiles"></a>메타 파일을 사용 하 여 컨트롤 그리기  
 대부분의 경우 `pdc` 함수에 대한 `OnDraw` 매개 변수는 화면 DC(장치 컨텍스트)를 가리킵니다. 그러나 컨트롤의 이미지를 그릴 때 또는 인쇄 미리 보기 세션 중 렌더링을 위해 받은 DC는 "메타파일 DC"라는 특별한 형식입니다. 전송된 요청을 즉시 처리하는 화면 DC와는 달리 메타파일 DC는 나중에 재생하기 위해 요청을 저장합니다. 일부 컨테이너 응용 프로그램은 디자인 모드에서 메타파일 DC를 사용하여 컨트롤 이미지를 렌더링하도록 선택할 수도 있습니다.  
  
 두 인터페이스 함수를 통해 컨테이너에 의해 메타 파일 그리기 요청을 만들 수 있습니다: **IViewObject::Draw** (이 함수 라고도 비 메타 파일 그리기에 대 한) 및 **idataobject:: Getdata**합니다. MFC 프레임 워크를 호출 하는 경우에 메타 파일 DC 매개 변수 중 하나로 전달 됩니다 [colecontrol:: Ondrawmetafile](../mfc/reference/colecontrol-class.md#ondrawmetafile)합니다. 이 함수는 가상 멤버 함수이므로 특수한 처리 작업을 수행할 컨트롤 클래스에서 이 함수를 재정의합니다. 기본 동작은 `COleControl::OnDraw`를 호출합니다.  
  
 컨트롤이 화면 및 메타파일 장치 컨텍스트 모두에서 그려질 수 있는지 확인하려면 화면 및 메타파일 DC 모두에서 지원되는 멤버 함수만 사용해야 합니다. 좌표계는 픽셀 단위로 측정할 수 없다는 사실에 주의해야 합니다.  
  
 `OnDrawMetafile`의 기본 구현은 컨트롤의 `OnDraw` 함수를 호출하므로 `OnDrawMetafile`을 재정의하지 않는 경우 메타파일 및 화면 장치 컨텍스트 모두에 적합한 멤버 함수만 사용합니다. 다음은 메타파일 및 화면 장치 컨텍스트 모두에서 사용할 수 있는 `CDC` 멤버 함수의 하위 집합을 보여 줍니다. 이러한 함수에 대 한 자세한 내용은 클래스를 참조 하십시오. [CDC](../mfc/reference/cdc-class.md) 에 *MFC 참조*합니다.  
  
|Arc|BibBlt|Chord|  
|---------|------------|-----------|  
|**타원**|**이스케이프**|`ExcludeClipRect`|  
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|  
|`LineTo`|`MoveTo`|`OffsetClipRgn`|  
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|  
|`Pie`|**다각형**|`Polyline`|  
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|  
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|  
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|  
|`SelectPalette`|`SetBkColor`|`SetBkMode`|  
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|  
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|  
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|  
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|  
|`StretchBlt`|`TextOut`||  
  
 `CDC` 멤버 함수 이외에 메타파일 DC에서 호환되는 여러 다른 함수가 있습니다. 여기에 [CPalette::AnimatePalette](../mfc/reference/cpalette-class.md#animatepalette), [CFont::CreateFontIndirect](../mfc/reference/cfont-class.md#createfontindirect), 및의 세 멤버 함수 `CBrush`: [CreateBrushIndirect](../mfc/reference/cbrush-class.md#createbrushindirect), [CreateDIBPatternBrush](../mfc/reference/cbrush-class.md#createdibpatternbrush), 및 [CreatePatternBrush](../mfc/reference/cbrush-class.md#createpatternbrush)합니다.  
  
 메타 파일에 기록 되지 않는 함수는: [DrawFocusRect](../mfc/reference/cdc-class.md#drawfocusrect), [DrawIcon](../mfc/reference/cdc-class.md#drawicon), [DrawText](../mfc/reference/cdc-class.md#drawtext), [ExcludeUpdateRgn](../mfc/reference/cdc-class.md#excludeupdatergn), [FillRect](../mfc/reference/cdc-class.md#fillrect), [FrameRect](../mfc/reference/cdc-class.md#framerect), [GrayString](../mfc/reference/cdc-class.md#graystring), [InvertRect](../mfc/reference/cdc-class.md#invertrect), [ScrollDC](../mfc/reference/cdc-class.md#scrolldc), 및 [TabbedTextOut](../mfc/reference/cdc-class.md#tabbedtextout)합니다. 메타파일 DC가 실제로 장치와 연결되어 있지 않으므로 SetDIBits, GetDIBits 및 CreateDIBitmap을 메타파일 DC와 함께 사용할 수 없습니다. 대상으로 SetDIBitsToDevice 및 StretchDIBits를 메타파일 DC와 함께 사용할 수 있습니다. [CreateCompatibleDC](../mfc/reference/cdc-class.md#createcompatibledc), [CreateCompatibleBitmap](../mfc/reference/cbitmap-class.md#createcompatiblebitmap), 및 [CreateDiscardableBitmap](../mfc/reference/cbitmap-class.md#creatediscardablebitmap) 는 메타 파일 DC와 의미가 없습니다.  
  
 메타파일 DC를 사용할 때 고려해야 할 또 다른 점은 좌표계를 픽셀 단위로 측정할 수 없다는 것입니다. 이 따라서 그리기 코드가 사각형에 맞게 조정 해야 하는 모든 형식에 전달 `OnDraw` 에 `rcBounds` 매개 변수입니다. `rcBounds`가 컨트롤의 창 크기를 나타내므로 이를 통해 컨트롤 외부에 실수로 그리는 것이 방지됩니다.  
  
 컨트롤에 대한 메타파일 렌더링을 구현한 후 테스트 컨테이너를 사용하여 메타파일을 테스트합니다. 테스트 컨테이너에 액세스하는 방법은 [테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md) 를 참조하세요.  
  
#### <a name="to-test-the-controls-metafile-using-test-container"></a>테스트 컨테이너를 사용하여 컨트롤의 메타파일을 테스트하려면  
  
1.  테스트 컨테이너에서 **편집** 메뉴를 클릭 하 여 **새 컨트롤 삽입**합니다.  
  
2.  에 **새 컨트롤 삽입** 상자 컨트롤을 선택 하 고 클릭 **확인**합니다.  
  
     컨트롤이 테스트 컨테이너에 나타납니다.  
  
3.  에 **제어** 메뉴를 클릭 하 여 **메타 파일 그리기**합니다.  
  
     별도의 창이 표시되는 메타파일에 나타납니다. 이 창의 크기를 변경하여 배율이 컨트롤의 메타파일에 주는 영향을 볼 수 있습니다. 언제든지 이 창을 닫을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

