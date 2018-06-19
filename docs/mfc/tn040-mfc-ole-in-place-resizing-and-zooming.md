---
title: 'TN040: MFC OLE 내부 크기 조정 및 확대/축소 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf8b90aed96135967167c8048f775fc7530f85d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385007"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE 내부 크기 조정 및 확대/축소
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트는 내부 편집에 관련 된 문제가 어떻게 서버 해야 올바른 확대/축소를 수행 및 내부 크기 조정 설명 합니다. 내부 활성화 WYSIWYG 개념은 해당 컨테이너에서 한 단계 더 발전 라인 상태가 되며 서버를 서로 협력 하 고 특히 거의 OLE 사양을 동일한 방식으로 해석 합니다.  
  
 컨테이너 및 내부 활성화를 지 원하는 서버 간의 닫기 상호 작용으로 인해 유지 해야 하는 최종 사용자에 게의 여러 가지:  
  
-   프레젠테이션 표시 (에서 그려지는 메타 파일의 `COleServerItem::OnDraw` 재정의) 같습니다 정확 하 게 그리기 (점을 제외 하는 편집 도구 표시 되지 않습니다) 편집용으로 합니다.  
  
-   컨테이너에 확대/축소 서버 창이 너무 합니다!  
  
-   컨테이너와 서버 모두에 동일한 메트릭을 사용 하 여 편집에 대 한 개체를 표시 되어야 합니다. 즉,의 수에 따라 매핑 모드를 사용 하 여 *논리* 인치 당 픽셀-인치당: 디스플레이 장치에서 렌더링 하는 경우 물리적 픽셀입니다.  
  
> [!NOTE]
>  내부 활성화 (연결 됨) 포함 된 항목에만 적용 됩니다, 때문에 확대/축소 포함 된 개체에만 적용 됩니다. 에 표시 되는 Api 모두 `COleServerDoc` 및 `COleServerItem` 확대/축소에 사용 되는 합니다. 디버거가이 분리 되며에 대 한 이유는 연결 및 포함 된 항목에 대 한 유효한 함수만 중인 `COleServerItem` (이 통해 공통 구현을 사용할 수 있습니다) 및 포함 된 개체에 대해서만 사용할 수 있는 함수에는 `COleServerDoc` 클래스 (서버의 측면에서이 `document` 포함 되어 있는).  
  
 대부분의 부담을 서버에서 컨테이너의 확대/축소 비율을 알고 있어야 하 고 적절 하 게 편집 해당 인터페이스를 수정 해야 한다는 점에서 서버 구현자에 배치 됩니다. 하지만 서버가 컨테이너를 사용 하는 확대/축소 비율을 결정 방식  
  
## <a name="mfc-support-for-zooming"></a>확대/축소에 대 한 MFC 지원  
 호출 하 여 현재 확대/축소 비율을 확인할 수 있습니다 `COleServerDoc::GetZoomFactor`합니다. 이 문서에 내부 활성화 없는 경우 호출 항상 100% 확대/축소 비율 (또는 1:1 비율로)에 발생 합니다. 내부 활성화 100% 이외의 노드를 반환할 수 있습니다 하는 동안 그것을 호출 합니다.  
  
 확대/축소 수준은 올바르게 예제 보려면 MFC OLE 샘플 [HIERSVR](../visual-cpp-samples.md)합니다. 텍스트를 표시 하 고 텍스트를 일반적으로 확장 되지 않습니다 (힌트, 인쇄 규칙, 디자인 너비 및 높이 모든 해당 문제 복잡 하 게)를 순서 대로 복잡 HIERSVR에서 확대/축소 합니다. 그렇지만 HIERSVR은 올바르게, 확대/축소 구현에 대 한 적절 한 참조 이므로 MFC 자습서 [SCRIBBLE](../visual-cpp-samples.md) (단계 7).  
  
 `COleServerDoc::GetZoomFactor` 서로 다른 사용 가능한 메트릭 또는 컨테이너에서의 구현에서 수에 따라 확대/축소 비율을 결정 하면 `COleServerItem` 및 `COleServerDoc` 클래스입니다. 즉, 현재 확대/축소 비율 다음 수식에 의해 결정 됩니다.  
  
```  
Position Rectangle (PR) / Container Extent (CE)  
```  
  
 위치 사각형 컨테이너에 의해 결정 됩니다. 내부 활성화 동안 서버에 반환 하면 `COleClientItem::OnGetItemPosition` 호출 되 고 컨테이너 서버의 호출 될 때 업데이트 됩니다 `COleServerDoc::OnSetItemRects` (을 호출 하 여 `COleClientItem::SetItemRects`).  
  
 컨테이너 범위는 계산에 약간 더 복잡 합니다. 컨테이너를 호출한 경우 `COleServerItem::OnSetExtent` (을 호출 하 여 `COleClientItem::SetExtent`), 컨테이너 범위 논리 인치 당 픽셀 수에 따라 픽셀에 변환 된이 값은입니다. 컨테이너 SetExtent (이 일반적으로 경우)를 호출 하지 않은 경우 컨테이너 범위 내에서 반환 되는 크기는 `COleServerItem::OnGetExtent`합니다. 따라서 컨테이너가 SetExtent 호출 하는 경우 프레임 워크 가정 했을 경우 컨테이너는가 호출 되도록 것 자연 범위의 100% (에서 반환 된 값 **COleServerItem::GetExtent**). 즉, 프레임 워크 컨테이너가 항목의 100% (더 이상, no 작음)를 표시 하는 것으로 가정 합니다.  
  
 하지만 해야 `COleServerItem::OnSetExtent` 및 `COleServerItem::OnGetExtent` 이름이 유사한 항목의 동일한 특성을 조작 하지 않습니다. `OnSetExtent` 서버에서 개체의 표시 되는 (확대/축소 비율)에 관계 없이 컨테이너에서 파악 하기 위해 호출 하 고 `OnGetExtent` 개체의 이상적인 크기를 결정 하 고 컨테이너에 의해 호출 됩니다.  
  
 각 관련 된 Api를 살펴보면 좀더 명확한을 얻을 수 있습니다.  
  
## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent  
 이 함수를 HIMETRIC 단위의 항목의 "자연 크기"를 반환 해야 합니다. "자연 크기"의 개념으로 생각 인쇄할 때 나타나는 크기로 정의 하는 가장 좋은 방법은 합니다. 여기에 반환 되는 크기는 흡사는 메타 파일에는 특정 항목에 대 한 상수는 특정 항목 내용에 대 한 상수입니다. 이 크기는 항목에 적용 되는 확대/축소 변경 되지 않습니다. 일반적으로 바뀌지 않는 컨테이너 하면이 항목 다소간 공간 호출 하 여 `OnSetExtent`합니다. 예를 들어 변경은 줄 바꿈된 텍스트 컨테이너에서 보낸 마지막 범위에 따라 없습니다 "여백" 기능을 사용 하는 간단한 텍스트 편집기의 수도 있습니다. 서버 시스템 레지스트리에 비트 OLEMISC_RECOMPOSEONRESIZE을 설정 해야 하는 서버를 변경 하는 경우 (이 옵션에 대 한 자세한 내용은 OLE SDK 설명서 참조).  
  
## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent  
 이 함수는 컨테이너 "차이가" 개체의 표시 되 면 호출 됩니다. 대부분의 컨테이너를 호출 하지이 전혀 합니다. 기본 구현에 사용 되는 'm_sizeExtent' 컨테이너에서 받은 마지막 값을 저장 `COleServerDoc::GetZoomFactor` 위에서 설명한 컨테이너 범위 값을 계산 하는 경우.  
  
## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects  
 이 함수는 내부 활성 문서가 있는 경우에 호출 됩니다. 항목의 위치 또는 항목에 적용 클리핑 컨테이너를 업데이트할 때 호출 됩니다. 위치 사각형이, 위에서 설명한 것 처럼 제공 분자 확대/축소 비율 계산에 대 한 합니다. 항목 위치를 호출 하 여 변경할 수는 서버를 요청할 수 `COleServerDoc::RequestPositionChange`합니다. 컨테이너를 호출 하 여이 요청에 응답 하지 않을 수도 `OnSetItemRects` (호출 하 여 **COleServerItem::SetItemRects**).  
  
## <a name="coleserverdocondraw"></a>COleServerDoc::OnDraw  
 메타 파일의 재정의 하 여 만들어졌는지 실현 하려면 반드시 `COleServerItem::OnDraw` 정확히 동일한 메타 파일에 관계 없이 현재 확대/축소 비율을 생성 합니다. 컨테이너 메타 파일 적절 하 게 확장 됩니다. 이 중요 한 차이 보기의 `OnDraw` 및 서버 항목의 `OnDraw`합니다. 확대/축소 하 여 보기 핸들을 만들기만 항목을 *가능한* 메타 파일 및 확대/축소 적절 한 작업을 수행 하는 컨테이너의 몫입니다.  
  
 구현을 사용 하는 서버에 올바르게 동작 하도록 하는 가장 좋은 방법은 `COleServerDoc::GetZoomFactor` 문서가에 내부 활성화.  
  
## <a name="mfc-support-for-in-place-resizing"></a>내부 크기 조정에 대 한 MFC 지원  
 MFC OLE 2 사양에 설명 된 대로 완전 하 게 내부 크기 조정 인터페이스를 구현 합니다. 사용자 인터페이스에서 지원 되는 `COleResizeBar` 클래스를 사용자 지정 메시지 **WM_SIZECHILD**, 및에서이 메시지의 특수 처리 `COleIPFrameWnd`합니다.  
  
 프레임 워크에서 제공 되는 것 보다이 메시지의 다른 처리를 구현할 수도 있습니다. 프레임 워크 내부 컨테이너 최대 크기의 결과 벗어날 위에서 설명한 대로-서버에서의 확대/축소 비율 변경에 응답 합니다. 컨테이너는 둘 다 설정 하 여 반응 하는 경우 컨테이너 범위와 위치 사각형이 처리 하는 동안 해당 `COleClientItem::OnChangeItemPosition` (에 대 한 호출의 결과로 호출 `COleServerDoc::RequestPositionChange`) 내부 크기 조정 "차이가" 항목의 편집에 표시 될 한 다음 창입니다. 처리 하는 동안 위치 사각형을 설정 하 여 컨테이너에 반응 하는 경우 `COleClientItem::OnChangeItemPosition`확대/축소 비율 변경 되 고 "확대 또는 축소" 항목에 표시 됩니다,  
  
 서버에를 제어할 수 (어느 정도)이이 협상 하는 동안 수행 되는 작업입니다. 예를 들어 스프레드시트 셀을 표시 하려면 더 많거나 적은 항목을 편집 하는 동안 사용자가 창의 크기 조정 원위치에서 선택할 수 있습니다. word-processor 창와 동일 하 고 새 여백에 텍스트 줄을 바꿀 있도록 "페이지 여백을"를 변경 하도록 선택할 수 있습니다. 서버는이 자연 범위를 변경 하 여 구현 (에서 반환 되는 크기 `COleServerItem::OnGetExtent`) 크기 조정이 완료 되 면입니다. 이렇게 하면 위치 사각형이 컨테이너 범위에 동일한 확대/축소 비율을 더 큰 현상 보기 더 작은 영역 같은 값으로 변경할 수 있습니다. 또한, 차이가 문서에서 볼 수는 의해 생성 된 메타 파일 `OnDraw`합니다. 이 경우 문서 자체는 사용자의 보기 영역 대신 항목 크기를 조정할 때 변경 됩니다.  
  
 사용자 지정 크기 조정을 구현 하 고 제공한 사용자 인터페이스를 여전히 활용할 수 있습니다 `COleResizeBar` 재정의 하 여는 **WM_SIZECHILD** 메시지 프로그램 `COleIPFrameWnd` 클래스입니다. 세부 사항에 대 한 자세한 내용은 **WM_SIZECHILD**, 참조 [Technical Note 24](../mfc/tn024-mfc-defined-messages-and-resources.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

