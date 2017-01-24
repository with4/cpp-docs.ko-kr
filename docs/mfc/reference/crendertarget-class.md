---
title: "CRenderTarget 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRenderTarget"
  - "afxrendertarget/CRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRenderTarget 클래스"
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRenderTarget 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1RenderTarget에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CRenderTarget : public CObject;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRenderTarget::CRenderTarget](../Topic/CRenderTarget::CRenderTarget.md)|CRenderTarget 개체를 생성합니다.|  
|[CRenderTarget::~CRenderTarget](../Topic/CRenderTarget::~CRenderTarget.md)|소멸자  렌더링 대상 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRenderTarget::Attach](../Topic/CRenderTarget::Attach.md)|개체에 기존 렌더링 대상 인터페이스를 연결합니다.|  
|[CRenderTarget::BeginDraw](../Topic/CRenderTarget::BeginDraw.md)|이 렌더링 대상의 그리기를 시작합니다.|  
|[CRenderTarget::Clear](../Topic/CRenderTarget::Clear.md)|그리기 영역을 지정한 색으로 지웁니다.|  
|[CRenderTarget::COLORREF\_TO\_D2DCOLOR](../Topic/CRenderTarget::COLORREF_TO_D2DCOLOR.md)|GDI 색과 알파 값을 D2D1\_COLOR\_F 개체로 변환합니다.|  
|[CRenderTarget::CreateCompatibleRenderTarget](../Topic/CRenderTarget::CreateCompatibleRenderTarget.md)|현재 렌더링 대상과 호환되는 중간 오프스크린 그리기 중에 사용할 새 비트맵 렌더링 대상을 만듭니다.|  
|[CRenderTarget::Destroy](../Topic/CRenderTarget::Destroy.md)|하나 이상의 리소스를 삭제합니다.|  
|[CRenderTarget::Detach](../Topic/CRenderTarget::Detach.md)|개체에서 렌더링 대상 인터페이스를 분리합니다.|  
|[CRenderTarget::DrawBitmap](../Topic/CRenderTarget::DrawBitmap.md)|지정된 IDWriteTextLayout 개체에서 설명하는 서식 있는 텍스트를 그립니다.|  
|[CRenderTarget::DrawEllipse](../Topic/CRenderTarget::DrawEllipse.md)|지정된 스트로크 스타일을 사용하여 지정된 타원의 윤곽선을 그립니다.|  
|[CRenderTarget::DrawGeometry](../Topic/CRenderTarget::DrawGeometry.md)|지정된 스트로크 스타일을 사용하여 지정된 기하 도형의 윤곽선을 그립니다.|  
|[CRenderTarget::DrawGlyphRun](../Topic/CRenderTarget::DrawGlyphRun.md)|지정한 문자를 그립니다.|  
|[CRenderTarget::DrawLine](../Topic/CRenderTarget::DrawLine.md)|지정된 스트로크 스타일을 사용하여 지정된 점 사이에 선을 그립니다.|  
|[CRenderTarget::DrawRectangle](../Topic/CRenderTarget::DrawRectangle.md)|지정된 차원과 스트로크 스타일을 가진 사각형의 윤곽선을 그립니다.|  
|[CRenderTarget::DrawRoundedRectangle](../Topic/CRenderTarget::DrawRoundedRectangle.md)|지정된 스트로크 스타일을 사용하여 지정된 모퉁이가 둥근 사각형의 윤곽선을 그립니다.|  
|[CRenderTarget::DrawText](../Topic/CRenderTarget::DrawText.md)|IDWriteTextFormat 개체에서 제공하는 형식 정보를 사용하여 지정한 텍스트를 그립니다.|  
|[CRenderTarget::DrawTextLayout](../Topic/CRenderTarget::DrawTextLayout.md)|지정된 IDWriteTextLayout 개체에서 설명하는 서식 있는 텍스트를 그립니다.|  
|[CRenderTarget::EndDraw](../Topic/CRenderTarget::EndDraw.md)|렌더링 대상에서 그리기 작업을 끝내고 현재 오류 상태 및 관련된 태그를 나타냅니다.|  
|[CRenderTarget::FillEllipse](../Topic/CRenderTarget::FillEllipse.md)|지정된 타원의 내부를 그립니다.|  
|[CRenderTarget::FillGeometry](../Topic/CRenderTarget::FillGeometry.md)|지정된 기하 도형의 내부를 그립니다.|  
|[CRenderTarget::FillMesh](../Topic/CRenderTarget::FillMesh.md)|지정된 메시의 내부를 그립니다.|  
|[CRenderTarget::FillOpacityMask](../Topic/CRenderTarget::FillOpacityMask.md)|지정한 비트맵에서 설명하는 불투명 마스크를 브러시에 적용하고 해당 브러시를 사용하여 렌더링 대상의 영역을 칠합니다.|  
|[CRenderTarget::FillRectangle](../Topic/CRenderTarget::FillRectangle.md)|지정된 사각형의 내부를 그립니다.|  
|[CRenderTarget::FillRoundedRectangle](../Topic/CRenderTarget::FillRoundedRectangle.md)|지정된 모퉁이가 둥근 사각형의 내부를 그립니다.|  
|[CRenderTarget::Flush](../Topic/CRenderTarget::Flush.md)|보류 중인 모든 그리기 명령을 실행합니다.|  
|[CRenderTarget::GetAntialiasMode](../Topic/CRenderTarget::GetAntialiasMode.md)|텍스트가 아닌 그리기 작업에 대한 현재 앤티엘리어싱 모드를 검색합니다.|  
|[CRenderTarget::GetDpi](../Topic/CRenderTarget::GetDpi.md)|렌더링 대상의 DPI\(인치당 도트 수\)를 반환합니다.|  
|[CRenderTarget::GetMaximumBitmapSize](../Topic/CRenderTarget::GetMaximumBitmapSize.md)|렌더링 대상에서 지원하는 한 비트맵 차원의 장치 종속적 단위\(픽셀\)로 최대 크기를 가져옵니다.|  
|[CRenderTarget::GetPixelFormat](../Topic/CRenderTarget::GetPixelFormat.md)|렌더링 대상의 픽셀 형식 및 알파 모드를 검색합니다.|  
|[CRenderTarget::GetPixelSize](../Topic/CRenderTarget::GetPixelSize.md)|장치 픽셀로 렌더링 대상의 크기를 반환합니다.|  
|[CRenderTarget::GetRenderTarget](../Topic/CRenderTarget::GetRenderTarget.md)|ID2D1RenderTarget 인터페이스를 반환합니다.|  
|[CRenderTarget::GetSize](../Topic/CRenderTarget::GetSize.md)|장치 독립적인 픽셀로 렌더링 대상의 크기를 반환합니다.|  
|[CRenderTarget::GetTags](../Topic/CRenderTarget::GetTags.md)|이후 그리기 작업에 대한 레이블을 가져옵니다.|  
|[CRenderTarget::GetTextAntialiasMode](../Topic/CRenderTarget::GetTextAntialiasMode.md)|텍스트와 문자 모양 그리기 작업에 대한 현재 앤티엘리어싱 모드를 가져옵니다.|  
|[CRenderTarget::GetTextRenderingParams](../Topic/CRenderTarget::GetTextRenderingParams.md)|렌더링 대상의 현재 텍스트 렌더링 옵션을 검색합니다.|  
|[CRenderTarget::GetTransform](../Topic/CRenderTarget::GetTransform.md)|렌더링 대상에 지정된 변환을 적용하여 기존 변환을 바꿉니다.  이후의 모든 그리기 작업은 변환된 공간에서 발생합니다.|  
|[CRenderTarget::IsSupported](../Topic/CRenderTarget::IsSupported.md)|렌더링 대상이 지정된 속성을 지원하는지 여부를 나타냅니다.|  
|[CRenderTarget::IsValid](../Topic/CRenderTarget::IsValid.md)|리소스 유효성 검사|  
|[CRenderTarget::PopAxisAlignedClip](../Topic/CRenderTarget::PopAxisAlignedClip.md)|렌더링 대상에서 마지막 축에 맞춰진 클립을 제거합니다.  이 메서드를 호출한 후에 클립은 이후 그리기 작업에 더 이상 적용되지 않습니다.|  
|[CRenderTarget::PopLayer](../Topic/CRenderTarget::PopLayer.md)|마지막 PushLayer 호출에 의해 지정된 레이어로 그리기 작업을 리디렉션하는 것을 중지합니다.|  
|[CRenderTarget::PushAxisAlignedClip](../Topic/CRenderTarget::PushAxisAlignedClip.md)|렌더링 대상에서 마지막 축에 맞춰진 클립을 제거합니다.  이 메서드를 호출한 후에 클립은 이후 그리기 작업에 더 이상 적용되지 않습니다.|  
|[CRenderTarget::PushLayer](../Topic/CRenderTarget::PushLayer.md)|PopLayer가 호출될 때까지 모든 이후 그리기 작업을 수신하도록 렌더링 대상에 지정된 레이어를 추가합니다.|  
|[CRenderTarget::RestoreDrawingState](../Topic/CRenderTarget::RestoreDrawingState.md)|렌더링 대상의 그리기 상태를 지정된 ID2D1DrawingStateBlock의 상태로 설정합니다.|  
|[CRenderTarget::SaveDrawingState](../Topic/CRenderTarget::SaveDrawingState.md)|현재 그리기 상태를 지정된 ID2D1DrawingStateBlock에 저장합니다.|  
|[CRenderTarget::SetAntialiasMode](../Topic/CRenderTarget::SetAntialiasMode.md)|렌더링 대상의 앤티 앨리어싱 모드를 설정합니다.  앤티앨리어싱 모드는 텍스트와 문자 모양 그리기 작업을 제외하고 모든 후속 그리기 작업에 적용됩니다.|  
|[CRenderTarget::SetDpi](../Topic/CRenderTarget::SetDpi.md)|렌더링 대상의 DPI\(인치당 도트 수\)를 설정합니다.|  
|[CRenderTarget::SetTags](../Topic/CRenderTarget::SetTags.md)|후속 그리기 작업에 대한 레이블을 지정합니다.|  
|[CRenderTarget::SetTextAntialiasMode](../Topic/CRenderTarget::SetTextAntialiasMode.md)|후속 텍스트와 문자 모양 그리기 작업에 사용할 앤티엘리어싱 모드를 지정합니다.|  
|[CRenderTarget::SetTextRenderingParams](../Topic/CRenderTarget::SetTextRenderingParams.md)|모든 후속 텍스트와 문자 모양 그리기 작업에 적용할 텍스트 렌더링 옵션을 지정합니다.|  
|[CRenderTarget::SetTransform](../Topic/CRenderTarget::SetTransform.md)|오버로드.  렌더링 대상에 지정된 변환을 적용하여 기존 변환을 바꿉니다.  이후의 모든 그리기 작업은 변환된 공간에서 발생합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRenderTarget::VerifyResource](../Topic/CRenderTarget::VerifyResource.md)|CD2DResource 개체의 유효성을 확인하고, 아직 존재하지 않는 경우 개체를 만듭니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CRenderTarget::operator ID2D1RenderTarget\*](../Topic/CRenderTarget::operator%20ID2D1RenderTarget*.md)|ID2D1RenderTarget 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CRenderTarget::m\_lstResources](../Topic/CRenderTarget::m_lstResources.md)|CD2DResource 개체에 대한 포인터 목록입니다.|  
|[CRenderTarget::m\_pRenderTarget](../Topic/CRenderTarget::m_pRenderTarget.md)|ID2D1RenderTarget 개체에 대한 포인터입니다.|  
|[CRenderTarget::m\_pTextFormatDefault](../Topic/CRenderTarget::m_pTextFormatDefault.md)|기본 텍스트 서식을 포함하는 CD2DTextFormat 개체에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)