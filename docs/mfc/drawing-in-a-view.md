---
title: 뷰에 그리기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drawing [MFC], in views
- views [MFC], printing
- views [MFC], updating
- printing [MFC], views
- views [MFC], rendering
- printing views [MFC]
- paint messages in view class [MFC]
- device contexts, screen drawings
ms.assetid: e3761db6-0f19-4482-a4cd-ac38ef7c4d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 866f2e2a3de6708d1be78748ee889272a05352cd
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928501"
---
# <a name="drawing-in-a-view"></a>뷰에 그리기
보기의에서 발생 응용 프로그램에서 거의 모든 그리기 `OnDraw` 뷰 클래스에서 재정의 해야 하는 멤버 함수입니다. (예외가, 마우스 그리기에 [정도 보기를 통해 사용자 입력 해석](../mfc/interpreting-user-input-through-a-view.md).) 프로그램 `OnDraw` 재정의:  
  
1.  멤버 함수를 제공 하는 문서를 호출 하 여 데이터를 가져옵니다.  
  
2.  프레임 워크를 전달 하는 장치 컨텍스트 개체의 멤버 함수를 호출 하 여 데이터를 표시 합니다. `OnDraw`합니다.  
  
 문서의 데이터가 어떤 식으로든에서 변경 되 면 변경 내용을 반영 하도록 뷰가 다시 그려야 합니다. 일반적으로이 오류는 사용자가 문서에 대 한 뷰를 통해 변경할 때 발생 합니다. 보기에서 문서의 호출 하는 경우 [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) 멤버 함수를 업데이트 하려면 동일한 문서에 대해 모든 보기를 알립니다. `UpdateAllViews` 각 보기 호출 [OnUpdate](../mfc/reference/cview-class.md#onupdate) 멤버 함수입니다. 기본 구현은 `OnUpdate` 보기의 전체 클라이언트 영역을 무효화 합니다. 문서의 수정된 부분에 매핑되는 클라이언트 영역의 영역에만 무효화 하 여 재정의할 수 있습니다.  
  
 `UpdateAllViews` 클래스의 멤버 함수 `CDocument` 및 `OnUpdate` 클래스의 멤버 함수 `CView` 수정 된 문서 부분을 설명 하는 정보를 전달할 수 있습니다. 이 "힌트" 메커니즘을 사용 하는 뷰가 다시 그려야 하는 영역을 제한할 수 있습니다. `OnUpdate` 두 "힌트" 인수를 사용 합니다. 첫 번째 *lHint*, 형식의 **LPARAM**,에서는 두 번째 있지만 원하는 모든 데이터를 전달할 수 있습니다 *pHint*, 형식의 `CObject`*, 파생 된 개체에 대 한 포인터를 전달할 수 있습니다 `CObject`합니다.  
  
 보기 잘못 되 면 Windows 보냅니다는 **WM_PAINT** 메시지입니다. 보기의 [OnPaint](../mfc/reference/cwnd-class.md#onpaint) 클래스의 디바이스 컨텍스트 개체를 만들어 메시지에 응답 하는 처리기 함수 [CPaintDC](../mfc/reference/cpaintdc-class.md) 보기의 호출 `OnDraw` 멤버 함수입니다. 일반적으로 않아도 재정의 쓰려는 `OnPaint` 처리기 함수입니다.  
  
 A [디바이스 컨텍스트](../mfc/device-contexts.md) 화면 또는 프린터와 같은 장치의 그리기 특성에 대 한 정보를 포함 하는 Windows 데이터 구조입니다. 모든 그리기 호출은 디바이스 컨텍스트 개체를 통해 수행 됩니다. 그리기는 화면에 관한 `OnDraw` 전달 되는 `CPaintDC` 개체입니다. 프린터에서 그리기를 위해 전달 되는 [CDC](../mfc/reference/cdc-class.md) 개체가 현재 프린터에 대 한 설정입니다.  
  
 뷰에 그리기에 대 한 코드는 먼저 문서에 대 한 포인터를 검색 합니다. 다음 장치 컨텍스트를 통해 그리기 호출 합니다. 다음과 같은 간단한 `OnDraw` 예제 과정을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]  
  
 이 예제에서는 정의 `GetData` 파생된 문서 클래스의 구성원으로 작동 합니다.  
  
 보기에서 가운데 맞춤 하 여 문서에서 가져온 문자열을 출력 합니다. 경우는 `OnDraw` 화면 그리기 위해 호출 됩니다는 `CDC` 개체가 전달 된 *pDC* 는 `CPaintDC` 의 생성자가 이미 호출 `BeginPaint`합니다. 그리기 기능에 대 한 호출 디바이스 컨텍스트 포인터를 통해 이루어집니다. 장치 컨텍스트 및 그리기 호출에 대 한 내용은 클래스를 참조 하십시오. [CDC](../mfc/reference/cdc-class.md) 에 *MFC 참조* 및 [창 개체 작업](../mfc/working-with-window-objects.md)합니다.  
  
 작성 하는 방법의 예 `OnDraw`, 참조는 [MFC 샘플](../visual-cpp-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [뷰 사용](../mfc/using-views.md)

