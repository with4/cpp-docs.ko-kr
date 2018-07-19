---
title: 스크롤 및 뷰를 크기 조정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9758c63562a19d6b9e458fd434108a92bbc8576
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379270"
---
# <a name="scrolling-and-scaling-views"></a>뷰 스크롤 및 크기 조정
MFC는 뷰를 스크롤하여 뷰를 자동으로 표시 하는 프레임 창의 크기 측정을 지원 합니다. 클래스 `CScrollView` 두 종류의 보기를 지원 합니다.  
  
 스크롤 및 크기 조정 하는 방법에 대 한 자세한 내용은 참조 클래스 [CScrollView](../mfc/reference/cscrollview-class.md) 에 *MFC 참조*합니다. 스크롤 예 참조는 [Scribble 샘플](../visual-cpp-samples.md)합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   뷰 스크롤  
  
-   뷰의 크기 조정  
  
-   [보기 좌표](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a> 뷰 스크롤  
 자주 문서 크기 보기를 표시할 수 크기 보다 큽니다. 이 문서의 데이터 증가 또는 사용자가 보기 프레임 창을 축소 때문에 발생할 수 있습니다. 이 경우 스크롤 뷰 지원 해야 합니다.  
  
 모든 보기에 있는 스크롤 막대 메시지를 처리할 수는 `OnHScroll` 및 `OnVScroll` 멤버 함수입니다. 이러한 함수 중 하나가 구현 스크롤 막대 메시지 처리를 직접 모든 작업을 수행 하거나 사용할 수 있습니다는 `CScrollView` 스크롤을 처리 하는 클래스입니다.  
  
 `CScrollView`에서는 다음을 수행합니다.  
  
-   창과 뷰포트 크기와 매핑 모드 관리  
  
-   스크롤 막대 메시지에 응답 하 여 자동으로  
  
 (사용자가 스크롤 화살표를 클릭) 하는 경우 (사용자가 스크롤 막대 손잡이 클릭) 하는 경우는 "페이지" 및 "행"에 대 한 스크롤 얼마나 지정할 수 있습니다. 이러한 값이 보기의 특성에 맞게 계획 합니다. 예를 들어 다음 텍스트 문서에서 줄 높이에 따라 증가 하지만 그래픽 보기에 대 한 1 픽셀 단위로 스크롤해야는 것이 좋습니다.  
  
##  <a name="_core_scaling_a_view"></a> 뷰의 크기 조정  
 프레임 창 크기를 자동으로 맞게 보기를 사용할 때 사용할 수 있습니다 `CScrollView` 스크롤 대신 크기를 조정 합니다. 논리적 보기 늘어나거나 창의 클라이언트 영역에 꼭 맞게로 축소 합니다. 크기 조정 된 뷰는 스크롤 막대가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [뷰 사용](../mfc/using-views.md)

