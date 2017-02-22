---
title: "CDC 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDC 클래스"
  - "coordinates in Windows 95/98 [C++]"
  - "device contexts [C++], CDC 클래스"
  - "screen coordinates in device contexts"
  - "Windows[C++], device contexts"
  - "Windows 95 [C++], 화면 좌표"
  - "Windows 98 [C++], 화면 좌표"
ms.assetid: 715b3334-cb2b-4c9c-8067-02eb7c66c8b2
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDC 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디바이스 컨텍스트 개체의 클래스를 정의합니다.  
  
## 구문  
  
```  
class CDC : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDC::CDC](../Topic/CDC::CDC.md)|`CDC` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDC::AbortDoc](../Topic/CDC::AbortDoc.md)|지우기 모든 응용 프로그램의 마지막 호출 이후 장치에 기록 된 현재 인쇄 작업이 종료 되는 `StartDoc` 멤버 함수입니다.|  
|[CDC::AbortPath](../Topic/CDC::AbortPath.md)|장치 컨텍스트에서 모든 경로 무시 하 고 닫습니다.|  
|[CDC::AddMetaFileComment](../Topic/CDC::AddMetaFileComment.md)|주석 버퍼에서 지정 된 확장 형식 메타 파일에 복사합니다.|  
|[CDC::AlphaBlend](../Topic/CDC::AlphaBlend.md)|투명 또는 반투명 픽셀 비트맵을 표시 합니다.|  
|[CDC::AngleArc](../Topic/CDC::AngleArc.md)|선 세그먼트와 원호를 그립니다 및 호의 끝점으로 현재 위치를 이동 합니다.|  
|[CDC::Arc](../Topic/CDC::Arc.md)|타원 호를 그립니다.|  
|[CDC::ArcTo](../Topic/CDC::ArcTo.md)|타원 호를 그립니다.  이 함수에 유사 `Arc`, 현재 위치를 업데이트를 제외 하 고.|  
|[CDC::Attach](../Topic/CDC::Attach.md)|Windows 장치 컨텍스트의이 첨부 `CDC` 개체입니다.|  
|[CDC::BeginPath](../Topic/CDC::BeginPath.md)|장치 컨텍스트에서 경로 대괄호를 엽니다.|  
|[CDC::BitBlt](../Topic/CDC::BitBlt.md)|지정 된 디바이스 컨텍스트에서 비트맵을 복사합니다.|  
|[CDC::Chord](../Topic/CDC::Chord.md)|현 \(선분과 타원의 교차 부분으로 둘러싸인 닫힌된 그림\)를 그립니다.|  
|[CDC::CloseFigure](../Topic/CDC::CloseFigure.md)|경로에 있는 열린 그림을 닫습니다.|  
|[CDC::CreateCompatibleDC](../Topic/CDC::CreateCompatibleDC.md)|다른 디바이스 컨텍스트와 호환 되는 메모리 디바이스 컨텍스트를 만듭니다.  메모리에 이미지를 준비할 수 있습니다.|  
|[CDC::CreateDC](../Topic/CDC::CreateDC.md)|특정 장치에 대 한 장치 컨텍스트를 만듭니다.|  
|[CDC::CreateIC](../Topic/CDC::CreateIC.md)|특정 장치에 대 한 정보 컨텍스트를 만듭니다.  이 디바이스 컨텍스트를 만들지 않고 장치에 대 한 정보를 신속 하 게를 제공 합니다.|  
|[CDC::DeleteDC](../Topic/CDC::DeleteDC.md)|이와 관련 Windows 디바이스 컨텍스트를 삭제 합니다. `CDC` 개체입니다.|  
|[CDC::DeleteTempMap](../Topic/CDC::DeleteTempMap.md)|호출의 `CWinApp` 유휴 시간 모든 임시 삭제 처리기 `CDC` 개체에서 만든 `FromHandle`.  또한 장치 컨텍스트를 분리합니다.|  
|[CDC::Detach](../Topic/CDC::Detach.md)|Windows 장치 컨텍스트에서이 분리 `CDC` 개체입니다.|  
|[CDC::DPtoHIMETRIC](../Topic/CDC::DPtoHIMETRIC.md)|장치 단위로 변환  **HIMETRIC** 단위.|  
|[CDC::DPtoLP](../Topic/CDC::DPtoLP.md)|장치 단위 논리 단위로 변환합니다.|  
|[CDC::Draw3dRect](../Topic/CDC::Draw3dRect.md)|3 차원 사각형을 그립니다.|  
|[CDC::DrawDragRect](../Topic/CDC::DrawDragRect.md)|지우고이 끌 때 사각형을 다시 그립니다.|  
|[CDC::DrawEdge](../Topic/CDC::DrawEdge.md)|가장자리의 사각형을 그립니다.|  
|[CDC::DrawEscape](../Topic/CDC::DrawEscape.md)|그리기 그래픽 장치 인터페이스 \(GDI\) 통해 직접 사용할 수 있는 비디오 디스플레이의 기능에 액세스 합니다.|  
|[CDC::DrawFocusRect](../Topic/CDC::DrawFocusRect.md)|스타일에 포커스를 나타내는 데 사용 되는 사각형을 그립니다.|  
|[CDC::DrawFrameControl](../Topic/CDC::DrawFrameControl.md)|프레임 컨트롤을 그립니다.|  
|[CDC::DrawIcon](../Topic/CDC::DrawIcon.md)|아이콘을 그립니다.|  
|[CDC::DrawState](../Topic/CDC::DrawState.md)|이미지를 표시 하 고 상태를 나타내기 위해 시각 효과 적용 합니다.|  
|[CDC::DrawText](../Topic/CDC::DrawText.md)|서식 있는 텍스트 지정 된 사각형에를 그립니다.|  
|[CDC::DrawTextEx](../Topic/CDC::DrawTextEx.md)|서식 있는 텍스트 추가 형식을 사용 하 여 지정 된 사각형에를 그립니다.|  
|[CDC::Ellipse](../Topic/CDC::Ellipse.md)|타원을 그립니다.|  
|[CDC::EndDoc](../Topic/CDC::EndDoc.md)|인쇄 작업 시작 종료는 `StartDoc` 멤버 함수입니다.|  
|[CDC::EndPage](../Topic/CDC::EndPage.md)|페이지에서 종료 되는 장치 드라이버를 알립니다.|  
|[CDC::EndPath](../Topic/CDC::EndPath.md)|경로 대괄호 닫고 여는 대괄호 디바이스 컨텍스트에 정의 된 경로 선택 합니다.|  
|[CDC::EnumObjects](../Topic/CDC::EnumObjects.md)|펜을 열거 하 고 브러시 장치 컨텍스트에서 사용할 수 있습니다.|  
|[CDC::Escape](../Topic/CDC::Escape.md)|응용 프로그램을 GDI 통해 특정 장치에서 직접 사용할 수 없는 기능에 액세스할 수 있습니다.  또한 Windows 이스케이프 기능에 액세스할 수 있습니다.  이스케이프 호출 응용 프로그램에 의해 번역 되어 장치 드라이버에 전달 합니다.|  
|[CDC::ExcludeClipRect](../Topic/CDC::ExcludeClipRect.md)|\-지정 된 사각형 클리핑 영역의 기존 구성 새 클리핑 영역을 만듭니다.|  
|[CDC::ExcludeUpdateRgn](../Topic/CDC::ExcludeUpdateRgn.md)|드로잉을 창의 잘못 된 영역 내에서 클리핑 영역의 창에서에 업데이트 된 영역을 제외 하 여 수 없습니다.|  
|[CDC::ExtFloodFill](../Topic/CDC::ExtFloodFill.md)|현재 브러시 영역을 채웁니다.  보다 유연성을 제공 된 [CDC::FloodFill](../Topic/CDC::FloodFill.md) 멤버 함수입니다.|  
|[CDC::ExtTextOut](../Topic/CDC::ExtTextOut.md)|현재 선택한 글꼴을 사용 하 여 사각형 영역 내의 문자열을 씁니다.|  
|[CDC::FillPath](../Topic/CDC::FillPath.md)|현재 경로에 있는 열린 그림을 닫습니다 및 현재 브러시와 다각형 채우기 모드를 사용 하 여 경로의 내부를 채웁니다.|  
|[CDC::FillRect](../Topic/CDC::FillRect.md)|특정 브러시를 사용 하 여 지정 된 사각형을 채웁니다.|  
|[CDC::FillRgn](../Topic/CDC::FillRgn.md)|특정 지역 지정된 브러시로 채웁니다.|  
|[CDC::FillSolidRect](../Topic/CDC::FillSolidRect.md)|사각형을 단색으로 채웁니다.|  
|[CDC::FlattenPath](../Topic/CDC::FlattenPath.md)|현재 디바이스 컨텍스트로 선택한 경로에 있는 커브 변환 하 고 각 곡선 줄의 시퀀스를 설정 합니다.|  
|[CDC::FloodFill](../Topic/CDC::FloodFill.md)|현재 브러시 영역을 채웁니다.|  
|[CDC::FrameRect](../Topic/CDC::FrameRect.md)|사각형의 테두리를 그립니다.|  
|[CDC::FrameRgn](../Topic/CDC::FrameRgn.md)|브러시를 사용 하 여 특정 영역 주위에 테두리를 그립니다.|  
|[CDC::FromHandle](../Topic/CDC::FromHandle.md)|반환에 대 한 포인터는 `CDC` 개체 핸들 장치 컨텍스트를 지정 하면.  경우는 `CDC` 개체의 핸들을 임시 연결 되어 있지 않습니다 `CDC` 개체를 만들고 연결 합니다.|  
|[CDC::GetArcDirection](../Topic/CDC::GetArcDirection.md)|현재 호 방향에 대 한 장치 컨텍스트를 반환합니다.|  
|[CDC::GetAspectRatioFilter](../Topic/CDC::GetAspectRatioFilter.md)|가로 세로 비율이 현재 필터에 대 한 설정을 검색합니다.|  
|[CDC::GetBkColor](../Topic/CDC::GetBkColor.md)|현재 배경 색을 검색합니다.|  
|[CDC::GetBkMode](../Topic/CDC::GetBkMode.md)|백그라운드 모드를 검색합니다.|  
|[CDC::GetBoundsRect](../Topic/CDC::GetBoundsRect.md)|지정 된 장치 컨텍스트에 대 한 현재 누적 된 경계 사각형을 반환합니다.|  
|[CDC::GetBrushOrg](../Topic/CDC::GetBrushOrg.md)|현재 브러시 원점을 검색합니다.|  
|[CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)|현재 글꼴에서 지정 된 범위에서 연속 된 문자의 논리 단위 너비를 검색합니다.|  
|[CDC::GetCharABCWidthsI](../Topic/CDC::GetCharABCWidthsI.md)|연속 된 문자 모양 인덱스에서 지정 된 범위에서 현재 트루타입 글꼴의 논리 단위에서 너비를 검색합니다.|  
|[CDC::GetCharacterPlacement](../Topic/CDC::GetCharacterPlacement.md)|다양 한 유형의 문자열에 대 한 정보를 검색합니다.|  
|[CDC::GetCharWidth](../Topic/CDC::GetCharWidth.md)|현재 글꼴에서 좁은 너비의 지정 된 범위에서 연속 된 문자를 검색합니다.|  
|[CDC::GetCharWidthI](../Topic/CDC::GetCharWidthI.md)|현재 글꼴에서 지정 된 범위에서 연속 된 문자 모양 인덱스의 논리적 좌표에서는 너비를 검색합니다.|  
|[CDC::GetClipBox](../Topic/CDC::GetClipBox.md)|현재 클리핑 경계 tightest 경계 사각형의 크기를 검색합니다.|  
|[CDC::GetColorAdjustment](../Topic/CDC::GetColorAdjustment.md)|장치 컨텍스트에 대 한 색 조정 값을 검색합니다.|  
|[CDC::GetCurrentBitmap](../Topic/CDC::GetCurrentBitmap.md)|현재 선택한 포인터를 반환 합니다. `CBitmap` 개체입니다.|  
|[CDC::GetCurrentBrush](../Topic/CDC::GetCurrentBrush.md)|현재 선택한 포인터를 반환 합니다. `CBrush` 개체입니다.|  
|[CDC::GetCurrentFont](../Topic/CDC::GetCurrentFont.md)|현재 선택한 포인터를 반환 합니다. `CFont` 개체입니다.|  
|[CDC::GetCurrentPalette](../Topic/CDC::GetCurrentPalette.md)|현재 선택한 포인터를 반환 합니다. `CPalette` 개체입니다.|  
|[CDC::GetCurrentPen](../Topic/CDC::GetCurrentPen.md)|현재 선택한 포인터를 반환 합니다. `CPen` 개체입니다.|  
|[CDC::GetCurrentPosition](../Topic/CDC::GetCurrentPosition.md)|\(논리 좌표\)에서 펜의 현재 위치를 검색합니다.|  
|[CDC::GetDCBrushColor](../Topic/CDC::GetDCBrushColor.md)|현재 브러쉬 색을 검색합니다.|  
|[CDC::GetDCPenColor](../Topic/CDC::GetDCPenColor.md)|현재 펜 색을 검색합니다.|  
|[CDC::GetDeviceCaps](../Topic/CDC::GetDeviceCaps.md)|지정 된 일종의 특정된 디스플레이 장치의 기능에 대 한 장치별 정보를 검색합니다.|  
|[CDC::GetFontData](../Topic/CDC::GetFontData.md)|확장 가능한 글꼴 파일의 글꼴 메트릭 정보를 검색합니다.  정보를 검색 하는 글꼴 파일 및 길이를 반환 하는 정보에 오프셋을 지정 하 여 식별 됩니다.|  
|[CDC::GetFontLanguageInfo](../Topic/CDC::GetFontLanguageInfo.md)|지정한 디스플레이 컨텍스트를 현재 선택한 글꼴에 대 한 정보를 반환합니다.|  
|[CDC::GetGlyphOutline](../Topic/CDC::GetGlyphOutline.md)|곡선 개요 또는 비트맵 개요 현재 글꼴에서 문자를 검색합니다.|  
|[CDC::GetGraphicsMode](../Topic/CDC::GetGraphicsMode.md)|현재 모드는 지정 된 디바이스 컨텍스트를 검색합니다.|  
|[CDC::GetHalftoneBrush](../Topic/CDC::GetHalftoneBrush.md)|하프톤 브러시를 검색합니다.|  
|[CDC::GetKerningPairs](../Topic/CDC::GetKerningPairs.md)|커닝 쌍에 지정 된 디바이스 컨텍스트에서 현재 선택 된 글꼴의 문자를 검색 합니다.|  
|[CDC::GetLayout](../Topic/CDC::GetLayout.md)|장치 컨텍스트 \(DC\)의 레이아웃을 검색합니다.  레이아웃 \(기본값\) 오른쪽 또는 오른쪽에서 왼쪽은 남아 있을 수 있습니다 \(미러됨\).|  
|[CDC::GetMapMode](../Topic/CDC::GetMapMode.md)|현재 매핑 모드를 검색합니다.|  
|[CDC::GetMiterLimit](../Topic/CDC::GetMiterLimit.md)|마이터 한계에 대 한 장치 컨텍스트를 반환합니다.|  
|[CDC::GetNearestColor](../Topic/CDC::GetNearestColor.md)|지정 된 장치를 나타내는 지정 된 논리 색 논리 가장 가까운 색을 검색 합니다.|  
|[CDC::GetOutlineTextMetrics](../Topic/CDC::GetOutlineTextMetrics.md)|트루타입 글꼴을 글꼴 메트릭 정보를 검색합니다.|  
|[CDC::GetOutputCharWidth](../Topic/CDC::GetOutputCharWidth.md)|출력 장치 컨텍스트를 사용 하 여 현재 글꼴의 너비는 개별 문자의 연속 된 그룹의 문자를 검색 합니다.|  
|[CDC::GetOutputTabbedTextExtent](../Topic/CDC::GetOutputTabbedTextExtent.md)|너비와 높이의 문자열 출력 장치 컨텍스트를 계산합니다.|  
|[CDC::GetOutputTextExtent](../Topic/CDC::GetOutputTextExtent.md)|너비 및 높이 줄의 텍스트를 현재 글꼴 크기를 결정 하 여 출력 장치 컨텍스트를 계산 합니다.|  
|[CDC::GetOutputTextMetrics](../Topic/CDC::GetOutputTextMetrics.md)|현재 글꼴 메트릭을 출력 장치 컨텍스트를 검색합니다.|  
|[CDC::GetPath](../Topic/CDC::GetPath.md)|줄의 끝점과 제어점을 디바이스 컨텍스트로 선택한 경로에 있는 곡선을 정의 하는 좌표를 검색 합니다.|  
|[CDC::GetPixel](../Topic/CDC::GetPixel.md)|지정 된 위치의 픽셀의 RGB 색상 값을 검색합니다.|  
|[CDC::GetPolyFillMode](../Topic/CDC::GetPolyFillMode.md)|현재 다각형 채우기 모드를 검색합니다.|  
|[CDC::GetROP2](../Topic/CDC::GetROP2.md)|현재 그리기 모드를 검색합니다.|  
|[CDC::GetSafeHdc](../Topic/CDC::GetSafeHdc.md)|반환 [CDC::m\_hDC](../Topic/CDC::m_hDC.md), 출력 장치 컨텍스트.|  
|[CDC::GetStretchBltMode](../Topic/CDC::GetStretchBltMode.md)|현재 비트맵 늘이기 모드를 검색합니다.|  
|[CDC::GetTabbedTextExtent](../Topic/CDC::GetTabbedTextExtent.md)|너비 및 높이 특성 장치 컨텍스트 문자열을 계산합니다.|  
|[CDC::GetTextAlign](../Topic/CDC::GetTextAlign.md)|텍스트 맞춤 플래그를 검색합니다.|  
|[CDC::GetTextCharacterExtra](../Topic/CDC::GetTextCharacterExtra.md)|Intercharacter 간격의 현재 설정을 검색합니다.|  
|[CDC::GetTextColor](../Topic/CDC::GetTextColor.md)|현재 텍스트 색을 검색합니다.|  
|[CDC::GetTextExtent](../Topic/CDC::GetTextExtent.md)|너비 및 높이 줄의 텍스트를 현재 글꼴 크기를 확인 하 여 특성 장치 컨텍스트를 계산 합니다.|  
|[CDC::GetTextExtentExPointI](../Topic/CDC::GetTextExtentExPointI.md)|지정 된 공간에 적합 한 배열을 텍스트 범위를 각 이러한 문자에 대 한 채우기 지정 된 문자열의 문자 수를 검색 합니다.|  
|[CDC::GetTextExtentPointI](../Topic/CDC::GetTextExtentPointI.md)|너비와 높이 지정된 된 문자 모양 인덱스의 배열 검색합니다.|  
|[CDC::GetTextFace](../Topic/CDC::GetTextFace.md)|현재 글꼴의 서체 이름을 버퍼에 null로 끝나는 문자열로 복사합니다.|  
|[CDC::GetTextMetrics](../Topic/CDC::GetTextMetrics.md)|현재 글꼴 메트릭을 특성 장치 컨텍스트를 검색합니다.|  
|[CDC::GetViewportExt](../Topic/CDC::GetViewportExt.md)|뷰포트의 x\-및 y\-익스텐트를 검색합니다.|  
|[CDC::GetViewportOrg](../Topic/CDC::GetViewportOrg.md)|뷰포트 원점 x 및 y 좌표를 검색합니다.|  
|[CDC::GetWindow](../Topic/CDC::GetWindow.md)|디스플레이 디바이스 컨텍스트와 연결 된 창을 반환 합니다.|  
|[CDC::GetWindowExt](../Topic/CDC::GetWindowExt.md)|관련된 윈도우의 x\-및 y\-익스텐트를 검색합니다.|  
|[CDC::GetWindowOrg](../Topic/CDC::GetWindowOrg.md)|연결 된 창 원점 x 및 y 좌표를 검색합니다.|  
|[CDC::GetWorldTransform](../Topic/CDC::GetWorldTransform.md)|현재 월드 공간 변환 페이지 공간을 검색합니다.|  
|[CDC::GradientFill](../Topic/CDC::GradientFill.md)|사각형과 삼각형 구조를 gradating 색상으로 채웁니다.|  
|[CDC::GrayString](../Topic/CDC::GrayString.md)|그립니다 \(회색된\) 텍스트를 특정된 위치에 흐리게 표시 됩니다.|  
|[CDC::HIMETRICtoDP](../Topic/CDC::HIMETRICtoDP.md)|변환  **HIMETRIC** 단위 장치 단위로 합니다.|  
|[CDC::HIMETRICtoLP](../Topic/CDC::HIMETRICtoLP.md)|변환  **HIMETRIC** 단위를 논리 단위로 합니다.|  
|[CDC::IntersectClipRect](../Topic/CDC::IntersectClipRect.md)|현재 영역 사각형의 교차 부분을 형성 하 여 새로운 클리핑 영역을 만듭니다.|  
|[CDC::InvertRect](../Topic/CDC::InvertRect.md)|사각형의 내용을 반전 시킵니다.|  
|[CDC::InvertRgn](../Topic/CDC::InvertRgn.md)|색 영역에서을 반전합니다.|  
|[CDC::IsPrinting](../Topic/CDC::IsPrinting.md)|디바이스 컨텍스트 인쇄에 사용 되는지 여부를 결정 합니다.|  
|[CDC::LineTo](../Topic/CDC::LineTo.md)|현재 위치까지 등을 제외한 지점에서 줄을 그립니다.|  
|[CDC::LPtoDP](../Topic/CDC::LPtoDP.md)|논리 단위 장치 단위로 변환합니다.|  
|[CDC::LPtoHIMETRIC](../Topic/CDC::LPtoHIMETRIC.md)|논리 단위로 변환  **HIMETRIC** 단위.|  
|[CDC::MaskBlt](../Topic/CDC::MaskBlt.md)|지정 된 마스크와 래스터 작업을 사용 하 여 원본 및 대상 비트맵에 대 한 색 데이터를 결합 합니다.|  
|[CDC::ModifyWorldTransform](../Topic/CDC::ModifyWorldTransform.md)|전역 변환은 지정 된 모드를 사용 하는 디바이스 컨텍스트에 대 한 변경 됩니다.|  
|[CDC::MoveTo](../Topic/CDC::MoveTo.md)|현재 위치를 이동합니다.|  
|[CDC::OffsetClipRgn](../Topic/CDC::OffsetClipRgn.md)|클리핑 영역을 지정 된 장치를 이동합니다.|  
|[CDC::OffsetViewportOrg](../Topic/CDC::OffsetViewportOrg.md)|현재 뷰포트 원점 좌표를 기준으로 뷰포트를 수정합니다.|  
|[CDC::OffsetWindowOrg](../Topic/CDC::OffsetWindowOrg.md)|창 원점을 현재 창 원점 좌표를 기준으로 수정합니다.|  
|[CDC::PaintRgn](../Topic/CDC::PaintRgn.md)|선택한 브러시로 영역을 채웁니다.|  
|[CDC::PatBlt](../Topic/CDC::PatBlt.md)|비트 패턴을 만듭니다.|  
|[CDC::Pie](../Topic/CDC::Pie.md)|원형 모양의 쐐기를 그립니다.|  
|[CDC::PlayMetaFile](../Topic/CDC::PlayMetaFile.md)|지정 된 메타 파일의 내용을 지정 된 장치에서 재생 됩니다.  향상 된 버전의 `PlayMetaFile` 지정 된 확장 형식 메타 파일에 저장 된 그림을 표시 합니다.  메타 파일을 여러 번 재생할 수 있습니다.|  
|[CDC::PlgBlt](../Topic/CDC::PlgBlt.md)|비트 블록 전송 비트 색 데이터의 원본 장치 컨텍스트에서 지정 된 사각형에서 지정 된 장치 컨텍스트를 지정 된 평행 사변형에 수행합니다.|  
|[CDC::PolyBezier](../Topic/CDC::PolyBezier.md)|하나 이상의 Bzier 스플라인을 그립니다.  현재 위치 사용도 업데이트 됩니다.|  
|[CDC::PolyBezierTo](../Topic/CDC::PolyBezierTo.md)|하나 이상의 Bzier 스플라인 그리고 마지막 Bzier 스플라인 끝점을 현재 위치를 이동 합니다.|  
|[CDC::PolyDraw](../Topic/CDC::PolyDraw.md)|Bzier 스플라인 및 선 세그먼트를 그립니다.  이 함수는 현재 위치를 업데이트합니다.|  
|[CDC::Polygon](../Topic/CDC::Polygon.md)|선으로 연결 된 두 개 이상의 지점 \(꼭지점\)으로 구성 된 다각형을 그립니다.|  
|[CDC::Polyline](../Topic/CDC::Polyline.md)|지정 된 지점에 연결 된 선 세그먼트를 그립니다.|  
|[CDC::PolylineTo](../Topic/CDC::PolylineTo.md)|현재 위치를 마지막 줄의 끝 지점으로 이동 하 고 하나 이상의 직선을 그립니다.|  
|[CDC::PolyPolygon](../Topic/CDC::PolyPolygon.md)|현재 다각형 채우기 모드를 사용 하 여 채워진 다각형 두 개 이상 만듭니다.  다각형 분리 되었거나 서로 겹칠 수 있습니다.|  
|[CDC::PolyPolyline](../Topic/CDC::PolyPolyline.md)|여러 일련의 연결 된 선 세그먼트를 그립니다.  현재 위치 사용 되 지도에서이 함수를 업데이트 합니다.|  
|[CDC::PtVisible](../Topic/CDC::PtVisible.md)|특정된 지점에서 클리핑 영역의 인지 여부를 지정 합니다.|  
|[CDC::RealizePalette](../Topic/CDC::RealizePalette.md)|색상표 항목을 현재 논리 색상표에서를 시스템 색상표에 매핑합니다.|  
|[CDC::Rectangle](../Topic/CDC::Rectangle.md)|현재 펜을 사용 하 여 직사각형 그리고 현재 브러시를 사용 하 여 채웁니다.|  
|[CDC::RectVisible](../Topic/CDC::RectVisible.md)|지정 된 사각형의 일부 클리핑 영역 내에 있는지 여부를 결정 합니다.|  
|[CDC::ReleaseAttribDC](../Topic/CDC::ReleaseAttribDC.md)|릴리스 `m_hAttribDC`, 특성 장치 컨텍스트.|  
|[CDC::ReleaseOutputDC](../Topic/CDC::ReleaseOutputDC.md)|릴리스 `m_hDC`, 출력 장치 컨텍스트.|  
|[CDC::ResetDC](../Topic/CDC::ResetDC.md)|업데이트는 `m_hAttribDC` 장치 컨텍스트.|  
|[CDC::RestoreDC](../Topic/CDC::RestoreDC.md)|장치 컨텍스트 저장 이전 상태로 복원 `SaveDC`.|  
|[CDC::RoundRect](../Topic/CDC::RoundRect.md)|현재 펜을 사용 하 고 현재 브러시를 사용 하 여 채워진 모퉁이가 둥근된 사각형을 그립니다.|  
|[CDC::SaveDC](../Topic/CDC::SaveDC.md)|디바이스 컨텍스트의 현재 상태를 저장합니다.|  
|[CDC::ScaleViewportExt](../Topic/CDC::ScaleViewportExt.md)|뷰포트 범위에 대해 현재 값을 수정합니다.|  
|[CDC::ScaleWindowExt](../Topic/CDC::ScaleWindowExt.md)|현재 값을 기준으로 창의 범위를 수정합니다.|  
|[CDC::ScrollDC](../Topic/CDC::ScrollDC.md)|비트는 직사각형 가로 및 세로로 스크롤합니다.|  
|[CDC::SelectClipPath](../Topic/CDC::SelectClipPath.md)|현재 경로 클리핑 영역의 디바이스 컨텍스트를 지정 된 모드를 사용 하 여 결합 하는 기존의 클리핑 영역과 새 영역을 선택 합니다.|  
|[CDC::SelectClipRgn](../Topic/CDC::SelectClipRgn.md)|지정 된 모드를 사용 하 여 현재 클리핑 영역으로 지정 된 영역을 결합 합니다.|  
|[CDC::SelectObject](../Topic/CDC::SelectObject.md)|펜 같은 GDI 그리기 개체를 선택합니다.|  
|[CDC::SelectPalette](../Topic/CDC::SelectPalette.md)|논리 색상표를 선택합니다.|  
|[CDC::SelectStockObject](../Topic/CDC::SelectStockObject.md)|미리 정의 된 스톡 펜, 브러시, 또는 Windows에서 제공 하는 글꼴 중 하나를 선택 합니다.|  
|[CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)|인쇄 작업을 중단 해야 하는 경우 Windows를 호출 하는 프로그래머가 제공한 콜백 함수를 설정 합니다.|  
|[CDC::SetArcDirection](../Topic/CDC::SetArcDirection.md)|호 및 사각형 함수를 사용 하 여 드로잉 방향을 설정 합니다.|  
|[CDC::SetAttribDC](../Topic/CDC::SetAttribDC.md)|세트 `m_hAttribDC`, 특성 장치 컨텍스트.|  
|[CDC::SetBkColor](../Topic/CDC::SetBkColor.md)|현재 배경 색을 설정 합니다.|  
|[CDC::SetBkMode](../Topic/CDC::SetBkMode.md)|백그라운드 모드를 설정합니다.|  
|[CDC::SetBoundsRect](../Topic/CDC::SetBoundsRect.md)|누적 된 경계 사각형 정보는 지정 된 장치 컨텍스트에 대 한 것을 제어합니다.|  
|[CDC::SetBrushOrg](../Topic/CDC::SetBrushOrg.md)|디바이스 컨텍스트로 선택한 다음 브러시의 원점을 지정 합니다.|  
|[CDC::SetColorAdjustment](../Topic/CDC::SetColorAdjustment.md)|지정 된 값을 사용 하는 디바이스 컨텍스트에 대 한 색 조정 값을 설정 합니다.|  
|[CDC::SetDCBrushColor](../Topic/CDC::SetDCBrushColor.md)|현재 브러쉬 색을 설정합니다.|  
|[CDC::SetDCPenColor](../Topic/CDC::SetDCPenColor.md)|현재 펜 색을 설정합니다.|  
|[CDC::SetGraphicsMode](../Topic/CDC::SetGraphicsMode.md)|지정 된 장치 컨텍스트에 대 한 현재 그래픽 모드를 설정 합니다.|  
|[CDC::SetLayout](../Topic/CDC::SetLayout.md)|장치 컨텍스트 \(DC\)의 레이아웃을 변경합니다.|  
|[CDC::SetMapMode](../Topic/CDC::SetMapMode.md)|현재 매핑 모드를 설정합니다.|  
|[CDC::SetMapperFlags](../Topic/CDC::SetMapperFlags.md)|논리적 글꼴이 실제 글꼴에 매핑되는 경우 글꼴 매퍼를 사용 하는 알고리즘을 변경 합니다.|  
|[CDC::SetMiterLimit](../Topic/CDC::SetMiterLimit.md)|장치 컨텍스트에 대 한 마이터 조인 길이 제한을 설정합니다.|  
|[CDC::SetOutputDC](../Topic/CDC::SetOutputDC.md)|세트 `m_hDC`, 출력 장치 컨텍스트.|  
|[CDC::SetPixel](../Topic/CDC::SetPixel.md)|지정 된 위치에 지정 된 색을 가장 가까운 근사치에 픽셀을 설정합니다.|  
|[CDC::SetPixelV](../Topic/CDC::SetPixelV.md)|지정 된 좌표에 가장 가까운 근사값의 지정 된 색 픽셀을 설정합니다.  `SetPixelV`보다 빠르게 `SetPixel` 그리고 실제로 포인트의 색상 값을 반환 하지 않아도 되므로.|  
|[CDC::SetPolyFillMode](../Topic/CDC::SetPolyFillMode.md)|다각형 채우기 모드를 설정합니다.|  
|[CDC::SetROP2](../Topic/CDC::SetROP2.md)|현재 그리기 모드를 설정합니다.|  
|[CDC::SetStretchBltMode](../Topic/CDC::SetStretchBltMode.md)|비트맵 늘이기 모드를 설정합니다.|  
|[CDC::SetTextAlign](../Topic/CDC::SetTextAlign.md)|텍스트 맞춤 플래그를 설정합니다.|  
|[CDC::SetTextCharacterExtra](../Topic/CDC::SetTextCharacterExtra.md)|Intercharacter 간격을 설정합니다.|  
|[CDC::SetTextColor](../Topic/CDC::SetTextColor.md)|텍스트 색을 설정합니다.|  
|[CDC::SetTextJustification](../Topic/CDC::SetTextJustification.md)|브레이크 문자 문자열에 공간을 추가합니다.|  
|[CDC::SetViewportExt](../Topic/CDC::SetViewportExt.md)|뷰포트의 x\-및 y\-익스텐트를 설정합니다.|  
|[CDC::SetViewportOrg](../Topic/CDC::SetViewportOrg.md)|뷰포트 원점을 설정합니다.|  
|[CDC::SetWindowExt](../Topic/CDC::SetWindowExt.md)|관련된 윈도우의 x\-및 y\-익스텐트를 설정합니다.|  
|[CDC::SetWindowOrg](../Topic/CDC::SetWindowOrg.md)|장치 컨텍스트 창 원점을 설정합니다.|  
|[CDC::SetWorldTransform](../Topic/CDC::SetWorldTransform.md)|현재 월드 공간 공간 페이지 변환을 설정합니다.|  
|[CDC::StartDoc](../Topic/CDC::StartDoc.md)|새 인쇄 작업을 시작 하 고 장치 드라이버를 알려줍니다.|  
|[CDC::StartPage](../Topic/CDC::StartPage.md)|새 페이지를 시작 하 고 장치 드라이버를 알려줍니다.|  
|[CDC::StretchBlt](../Topic/CDC::StretchBlt.md)|비트맵 소스 사각형 및 장치에서 늘이기 또는 필요한 경우 대상 사각형의 크기에 맞게 비트맵 압축을 대상 사각형으로 이동 합니다.|  
|[CDC::StrokeAndFillPath](../Topic/CDC::StrokeAndFillPath.md)|경로 열린 그림이, 패스의 윤곽선 현재 펜을 사용 하 여 발생을 닫고 현재 브러시를 사용 하 여 내부를 채웁니다.|  
|[CDC::StrokePath](../Topic/CDC::StrokePath.md)|현재 펜을 사용 하 여 지정 된 경로 렌더링 합니다.|  
|[CDC::TabbedTextOut](../Topic/CDC::TabbedTextOut.md)|탭을 확장 하 여 탭 위치 배열에 지정 된 값을 지정 된 위치에 문자열을 씁니다.|  
|[CDC::TextOut](../Topic/CDC::TextOut.md)|현재 선택한 글꼴을 사용 하 여 지정 된 위치에 문자열을 씁니다.|  
|[CDC::TransparentBlt](../Topic/CDC::TransparentBlt.md)|지정 된 색 투명 하 게 전송에서 렌더링 대상 장치 컨텍스트에 지정한 원본 장치 컨텍스트에서 비트 블록의 색상 데이터를 전송 합니다.|  
|[CDC::UpdateColors](../Topic/CDC::UpdateColors.md)|클라이언트 영역에서 현재 일치 하는 장치 컨텍스트의 클라이언트 영역에서 픽셀 단위로 시스템 색상표 색을 업데이트 합니다.|  
|[CDC::WidenPath](../Topic/CDC::WidenPath.md)|현재 경로 경로 디바이스 컨텍스트에 현재 선택 된 펜을 사용 하 여 스트로크 처리 된 경우에 그려야 하는 영역으로 다시 정의 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CDC::operator HDC](../Topic/CDC::operator%20HDC.md)|장치 컨텍스트 핸들을 검색합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDC::m\_hAttribDC](../Topic/CDC::m_hAttribDC.md)|특성 장치 컨텍스트를 사용 하 여이 `CDC` 개체입니다.|  
|[CDC::m\_hDC](../Topic/CDC::m_hDC.md)|출력 장치 컨텍스트를 사용 하 여이 `CDC` 개체입니다.|  
  
## 설명  
 `CDC` 개체 멤버 뿐만 아니라 디스플레이 또는 프린터 같은 장치 컨텍스트 디스플레이 컨텍스트 창의 클라이언트 영역과 관련 된 작업에 대 한 작업에 대 한 멤버 함수를 제공 합니다.  
  
 모든 드로잉을 통해 구성원의 기능 수행에 `CDC` 개체.  장치 컨텍스트 작업, 그리기 도구, 안전한 형식의 그래픽 장치 인터페이스 \(GDI\) 개체 선택 및 색상 및 팔레트 작업에 대 한 멤버 함수는 클래스를 제공 합니다.  또한 얻어 매핑, 뷰포트와 클리핑, 선 그리기 및 간단한 모양, 타원, 다각형 그리기 영역, 작업 좌표 변환 작업 창 크기와 작업 드로잉 특성을 설정 하기 위한 멤버 함수를 제공 합니다.  멤버 함수는 텍스트 그리기, 글꼴 작업, 프린터 이스케이프를 사용 하 여, 스크롤, 및 메타 파일 재생에 제공 됩니다.  
  
 사용 하는 `CDC` 개체를 생성 한 다음 해당 구성원 병렬 장치 컨텍스트를 사용 하는 Windows 함수는 함수 호출 합니다.  
  
> [!NOTE]
>  Windows 95\/98 모든 화면 좌표를 16 비트로 제한 됩니다.  따라서는 `int` 전달 하는 `CDC` 멤버 함수에 배치 해야의 범위 32768에서 32767에.  
  
 특정 용도 대 한 여러 클래스에서 파생 된 Mfc 라이브러리를 제공 `CDC` .  `CPaintDC`호출을 캡슐화 합니다. `BeginPaint` 및 `EndPaint`.  `CClientDC`창의 클라이언트 영역에 연결 된 디스플레이 컨텍스트를 관리 합니다.  `CWindowDC`프레임 및 컨트롤을 포함 하는 전체 창과 관련 한 디스플레이 컨텍스트를 관리 합니다.  `CMetaFileDC`장치 컨텍스트는 메타 파일에 연결합니다.  
  
 `CDC`두 개의 멤버 함수를 제공 합니다.  [GetLayout](../Topic/CDC::GetLayout.md) 및  [SetLayout](../Topic/CDC::SetLayout.md), 반대로 레이아웃 창에서 상속 되지 않은 장치 컨텍스트, 레이아웃에 대 한.  같은 오른쪽에서 왼쪽 방향 문화 아랍어나 히브리어 문자 레이아웃 유럽 표준 않습니다 작성 된 응용 프로그램에 필요 합니다.  
  
 `CDC`두 개의 디바이스 컨텍스트가 포함  [m\_hDC](../Topic/CDC::m_hDC.md) 및  [m\_hAttribDC](../Topic/CDC::m_hAttribDC.md)를 만들기에는 `CDC` 개체, 같은 장치를 참조 하십시오.  `CDC`모든 출력 GDI 호출을 지시 `m_hDC` 및 대부분의 특성이 GDI 호출에 `m_hAttribDC`.  \(호출 특성의 예로 `GetTextColor`, 동안 `SetTextColor` 는 출력 호출입니다.\)  
  
 예를 들어, 프레임 워크 이러한 두 장치 컨텍스트를 사용 하 여 구현 하는 `CMetaFileDC` 실제 장치에서 특성을 읽는 동안 메타 파일에 출력을 보낼 개체입니다.  인쇄 미리 보기의 프레임 워크에 유사한 방식으로 구현 됩니다.  두 장치 컨텍스트에 응용 프로그램별 코드에도 비슷한 방식으로 사용할 수 있습니다.  
  
 텍스트 메트릭 정보를 필요한 수 있습니다는 `m_hDC` 및 `m_hAttribDC` 장치 컨텍스트.  함수의 다음 쌍이이 기능을 제공 합니다.  
  
|M\_hAttribDC 사용|M\_hDC 사용|  
|---------------------|---------------|  
|[GetTextExtent](../Topic/CDC::GetTextExtent.md)|[GetOutputTextExtent](../Topic/CDC::GetOutputTextExtent.md)|  
|[GetTabbedTextExtent](../Topic/CDC::GetTabbedTextExtent.md)|[GetOutputTabbedTextExtent](../Topic/CDC::GetOutputTabbedTextExtent.md)|  
|[GetTextMetrics](../Topic/CDC::GetTextMetrics.md)|[GetOutputTextMetrics](../Topic/CDC::GetOutputTextMetrics.md)|  
|[GetCharWidth](../Topic/CDC::GetCharWidth.md)|[GetOutputCharWidth](../Topic/CDC::GetOutputCharWidth.md)|  
  
 에 대 한 자세한 내용은 `CDC`를 참조 하십시오  [장치 컨텍스트](../../mfc/device-contexts.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDC`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPaintDC Class](../../mfc/reference/cpaintdc-class.md)   
 [CWindowDC Class](../../mfc/reference/cwindowdc-class.md)   
 [CClientDC Class](../../mfc/reference/cclientdc-class.md)   
 [CMetaFileDC Class](../../mfc/reference/cmetafiledc-class.md)