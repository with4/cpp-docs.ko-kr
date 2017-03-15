---
title: "MFC ActiveX 컨트롤: ActiveX 컨트롤 그리기 | Microsoft Docs"
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
  - "MFC ActiveX 컨트롤, 최적화"
  - "MFC ActiveX 컨트롤, 그리기"
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC ActiveX 컨트롤: ActiveX 컨트롤 그리기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 ActiveX 컨트롤 그리기 프로세스와 프로세스를 최적화 하는 그리기 코드를 변경 하는 방법을 설명합니다. \([컨트롤 그리기 최적화](../mfc/optimizing-control-drawing.md)을 통해 이전에 선택 된 GDI 개체를 복원할 필요가 없기 때문에 개별적으로 컨트롤 그리기를 최적화 하는 방법을 알 수 있습니다.\)  모든 컨트롤이 그려진 후 컨테이너가 자동으로 복원할 수 원본 개체입니다.\)  
  
 이 기사의 예제에서는 기본 설정은 MFC ActiveX 컨트롤 마법사에 의해 생성된 컨트롤의 것입니다.  MFC ActiveX 컨트롤 마법사를 사용하여 컨트롤 기초 응용 프로그램을 만드는 방법에 대한 자세한 내용은 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)문서를 참조 하십시오.  
  
 다음 항목은 다음을 다룹니다:  
  
-   [그리기를 지원하기 위한 ActiveX 컨트롤 마법사에서 만든 코드와 컨트롤을 그리기 위한 전반적인 프로세스](#_core_the_painting_process_of_an_activex_control)  
  
-   [그리기 프로세스를 최적화하는 방법](#_core_optimizing_your_paint_code)  
  
-   [메타 파일을 사용하여 컨트롤을 그리는 방법](#_core_painting_your_control_using_metafiles)  
  
##  <a name="_core_the_painting_process_of_an_activex_control"></a> ActiveX 컨트롤의 그리기 프로세스  
 ActiveX 컨트롤이 처음 표시되거나 다시 그려 질 때, 그들은 하나의 중요한 구별은 MFC를 사용하여 개발 된 다른 응용 프로그램과 비슷한 도장 공정은 다음과 같습니다: ActiveX 컨트롤을 활성 또는 비활성 상태가 될 수 있습니다.  
  
 활성 컨트롤은 자식 창에서 ActiveX 컨트롤 컨테이너에 표시됩니다.  다른 창과 마찬가지로  `WM_PAINT`  메시지가 수신될 때 그리기 자체에 대한 책임이 있습니다.  컨트롤의 기본 클래스[COleControl](../mfc/reference/colecontrol-class.md)는  `OnPaint`  함수에서 이 메세지를 처리합니다.  기본 구현은 컨트롤에서  `OnDraw` 함수를 호출합니다.  
  
 비활성 컨트롤은 이와 다르게 그려집니다.  컨트롤이 활성화되면 창은 표시 되지 않거나 존재 하지 않게되어, 그리기 메시지를 받을 수 없습니다.  대신 컨트롤 컨테이너는 컨트롤의  `OnDraw`  함수를 직접 호출할 수 있습니다.  이것은  `OnPaint`  멤버 함수가 호출되지 않는 활성 컨트롤의 그리기 프로세스와 다릅니다.  
  
 앞에서 설명했듯이 컨트롤의 상태에 따라 ActiveX 컨트롤은 업데이트하는 방법입니다.  그러나 두 경우에 프레임 워크는 해당  `OnDraw`  멤버 함수를 호출하기 때문에 이 멤버 함수에서 그리기 코드의 대부분을 추가합니다.  
  
 `OnDraw`  멤버 함수에서 컨트롤 그리기를 처리합니다.  컨트롤이 활성화되면 컨트롤 컨테이너는  `OnDraw` 을 호출하여  컨트롤 컨테이너의 디바이스 컨텍스트에 컨트롤 사각형 영역의 좌표를 전달합니다.  
  
 `OnDraw`  멤버 함수에 프레임 워크에 의해 전달되는 사각형은 컨트롤 영역을 포함합니다.  제어가 활성화 된 경우, 왼쪽 위 모서리가 \(0, 0\)이고, 전달 디바이스 컨텍스트는 컨트롤을 포함한 자식 윈도우에 대한 것입니다.  컨트롤이 활성화되지 않은 경우는 왼쪽의 좌표는 반드시 \(0,0\) 대신 전달 된 디바이스 컨텍스트 컨트롤을 포함하는 컨트롤 컨테이너입니다.  
  
> [!NOTE]
>  다음의 수정사항은 중요합니다.  `OnDraw` 은 사각형의 왼쪽된 위 좌표가 \(0, 0\)과 같은지에 의존하지 않습니다.  `OnDraw` 에 전달된 사각형 안에만 그려야합니다.  사각형의 영역을 넘어 그릴 경우 예기치 않은 결과가 발생할 수 있습니다.  
  
 아래의 컨트롤 구현 파일에서 MFC ActiveX 컨트롤 마법사 \(. CPP\)에 의해 제공되는 디폴트의 구현은 흰색 브러시로 사각형을 페인트와 현재의 배경색으로 타원을 채웁니다.  
  
 [!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/CPP/mfc-activex-controls-painting-an-activex-control_1.cpp)]  
  
> [!NOTE]
>  컨트롤을 그릴 때, 당신은  `OnDraw` 함수에 *pdc* 매개 변수로 전달된 장치 컨텍스트의 상태에 대한 추측을 하지 말아야합니다.   때때로 장치 컨텍스트는 컨테이너 응용 프로그램에서 제공되고 반드시 기본 상태로 초기화되지 않습니다.  특히, 펜, 브러시, 색, 글꼴 및 그리기 코드에 종속 된 다른 리소스를 명시적으로 선택합니다.  
  
##  <a name="_core_optimizing_your_paint_code"></a> 그리기 코드 최적화  
 컨트롤이 올바르게 그려진 후, 다음 단계는  `OnDraw`  함수를 최적화하는 것입니다.  
  
 기본적으로 ActiveX 컨트롤 그리기 전체 컨트롤 영역을 그립니다.  이 간단한 컨트롤에 충분하지만, 업데이트가 필요한 부분 만이 아닌 전체 컨트롤, 다시 칠 경우 많은 경우에 컨트롤을 다시 칠하는 것은 빠른 것입니다.  
  
 `OnDraw`  함수는 다시 그려야 하는 컨트롤의 사각형 영역인  `rcInvalid` 을 전달하여 최적화하는 쉬운 방법을 제공합니다.   그리기 작업 속도를 높이려면 전체 컨트롤 영역보다 더 작은 일반적으로 이 영역을 사용합니다.  
  
##  <a name="_core_painting_your_control_using_metafiles"></a> 메타 파일을 사용하여 컨트롤 그리기  
 대부분의 경우에는  `OnDraw` 에  `pdc`  매개 변수는 화면 디바이스 컨텍스트 \(DC\)를 가리킵니다.  그러나, 제어 및 인쇄 미리보기 세션의 이미지를 인쇄 할 때, 렌더링을 위해 받은 DC는 "메타 파일 DC"라는 특수한 타입입니다.  화면 DC와는 달리 , 즉시 그것에 전송된 요청을 처리하고 나중에 재생되는 메타 파일 DC 상점의 요청을 처리합니다.  일부 컨테이너 응용 프로그램은 때 디자인 모드에서 메타 파일 DC를 사용하여 컨트롤의 이미지를 렌더링 할 수도 있습니다.  
  
 메타 파일 그리기 요청은 두 개의 인터페이스 함수를 통한 컨테이너에 의해 제작될 수있다:  **IViewObject::Draw** \(이 함수는 또한 비\-메타 파일 그리기에 대해 호출될 수 있습니다\) 및  **IDataObject::GetData**.  메타 파일 DC는 매개 변수 중 하나로 전달되면 MFC 프레임 워크는 [COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md)에 호출을 합니다.  가상 멤버 함수이기 때문에 특수한 처리 작업을 수행할 컨트롤 클래스에 서이 함수를 재정의 합니다.  기본 동작은  `COleControl::OnDraw`을 호출합니다.  
  
 확인 컨트롤이 화면과 메타 파일 디바이스 컨텍스트에 모두 그려 질 수 있도록하려면 화면 및 메타 파일 DC 모두에서 지원되는 유일한 멤버 함수를 사용해야합니다.  좌표계는 픽셀 단위로 측정 할 수 없다는 것을 알고 있어야합니다.  
  
 기본적으로  `OnDrawMetafile` 의 구현은  `OnDraw`  함수를 호출하기 때문에,  `OnDrawMetafile` 을 재정의 하지 않으면 메타 파일 및 화면 장치 컨텍스트에 적합한 멤버함수를 사용합니다.  다음은 메타 파일 및 화면 장치 컨텍스트 모두에서 사용할 수있는 `CDC`의 멤버 함수의 하위 집합을 보여줍니다.  이러한 함수에 대한 자세한 내용은 *MFC 참조*의 [CDC](../mfc/reference/cdc-class.md) 클래스를 확인하십시오.  
  
|Arc|BibBlt|Chord|  
|---------|------------|-----------|  
|**타원**|**이스케이프**|`ExcludeClipRect`|  
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|  
|`LineTo`|`MoveTo`|`OffsetClipRgn`|  
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|  
|`Pie`|**Polygon**|`Polyline`|  
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|  
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|  
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|  
|`SelectPalette`|`SetBkColor`|`SetBkMode`|  
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|  
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|  
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|  
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|  
|`StretchBlt`|`TextOut`||  
  
 `CDC`  멤버 함수이외에 , 메타 파일 DC에에서 호환되는 다른 여러 가지 함수가 있습니다.  [CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md),  [CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md)와 `CBrush` :  [CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md),  [CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md), 및  [CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md) 함수의 세 멤버 함수를 포함합니다.  
  
 메타 파일에 기록 되지 않은 함수:  [DrawFocusRect](../Topic/CDC::DrawFocusRect.md),  [DrawIcon](../Topic/CDC::DrawIcon.md),  [DrawText](../Topic/CDC::DrawText.md),  [ExcludeUpdateRgn](../Topic/CDC::ExcludeUpdateRgn.md),  [FillRect](../Topic/CDC::FillRect.md),  [FrameRect](../Topic/CDC::FrameRect.md),  [GrayString](../Topic/CDC::GrayString.md),  [InvertRect](../Topic/CDC::InvertRect.md),  [ScrollDC](../Topic/CDC::ScrollDC.md), 및  [TabbedTextOut](../Topic/CDC::TabbedTextOut.md).  메타 파일 DC는 실제로 장치와 연관되어 있지 않기 때문에, 메타 파일 DC SetDIBits, GetDIBits 및 CreateDIBitmap 사용할 수 없습니다.  대상으로 메타 파일 DC SetDIBitsToDevice 및 StretchDIBits를 사용할 수 있습니다.  [CreateCompatibleDC](../Topic/CDC::CreateCompatibleDC.md),  [CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md), 및  [CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md) 는 메타 파일 DC에 의미가 없습니다.  
  
 메타 파일 DC를 사용할 때 고려해야 할 또 다른 점은 좌표계를 픽셀 단위로 측정 할 수 있다는 것입니다.  모든 드로잉 코드는  `rcBounds`  매개 변수의  `OnDraw` 에 전달된 사각형에 맞게 조정해야 합니다.   `rcBounds` 은 컨트롤의 창 크기를 나타내기 때문에 이는 컨트롤 외부에 실수로 그림을 그리는 것을 방지합니다.  
  
 컨트롤에 대한 메타 파일 렌더링을 구현 한 후, 메타 파일을 테스트하기 위해 테스트 컨테이너를 사용합니다.  테스트 컨테이너에 액세스하는 방법에 대한 자세한 내용은 [Test Container를 사용하여 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md)를 참조하십시오.  
  
#### Test Container를 사용하여 컨트롤의 메타 파일을 테스트 하려면  
  
1.  컨테이너의  **편집** 메뉴 테스트에서   **새 컨트롤 삽입**을 클릭합니다.  
  
2.  **새 컨트롤 삽입** 상자에서 컨트롤을 선택하고 **확인**을 클릭합니다.  
  
     컨트롤은 테스트 컨테이너에 표시됩니다.  
  
3.  **컨트롤**  메뉴에서  **메타 파일 그리기**을 클릭합니다.  
  
     별도 창이 표시되는 메타 파일 나타납니다.  확장 컨트롤의 메타 파일에 미치는 영향을 보려면 이 창 크기를 변경할 수 있습니다.  언제든지 창을 닫을 수 있습니다.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)