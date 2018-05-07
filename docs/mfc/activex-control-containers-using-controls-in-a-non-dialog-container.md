---
title: 'ActiveX 컨트롤 컨테이너: 대화 상자가 아닌 컨테이너에서 컨트롤을 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16264e9b072d27349d4375bd7c04d5bbac1be597
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX 컨트롤 컨테이너: 대화 상자가 아닌 컨테이너에서 컨트롤 사용
일부 SDI 등의 응용 프로그램 또는 MDI 응용 프로그램을 응용 프로그램 창에 컨트롤을 포함 합니다. **만들기** 멤버 함수 Visual c + +에 의해 삽입 된 래퍼 클래스의 인스턴스를 만들 수는 컨트롤의 동적으로 대화 상자에 대 한 필요 없이 합니다.  
  
 **만들기** 멤버 함수에 다음 매개 변수:  
  
 `lpszWindowName`  
 포인터 (있는 경우) 컨트롤의 텍스트 또는 캡션 속성에 표시할 텍스트입니다.  
  
 `dwStyle`  
 창 스타일입니다. 전체 목록을 보려면를 참조 하십시오. [CWnd::CreateControl](../mfc/reference/cwnd-class.md#createcontrol)합니다.  
  
 `rect`  
 컨트롤의 크기와 위치를 지정합니다.  
  
 `pParentWnd`  
 일반적으로 컨트롤의 부모 창 지정을 `CDialog`합니다. 않아야 **NULL**합니다.  
  
 `nID`  
 컨트롤 ID를 지정 하 고 컨트롤을 참조 하는 컨테이너에서 사용할 수 있습니다.  
  
 이 함수를 사용 하 여 동적으로 ActiveX 컨트롤을 만드는 한 가지 예는 SDI 응용 프로그램의 폼 보기에서 것입니다. 그런 다음 컨트롤의 인스턴스를 만들 수는 `WM_CREATE` 응용 프로그램의 처리기입니다.  
  
 예를 들어 `CMyView` 는 기본 뷰 클래스 `CCirc` 래퍼 클래스 이며 가변 원형 H는 헤더 (합니다. H) 파일의 래퍼 클래스입니다.  
  
 이 기능을 구현 하는 것은 4 단계 프로세스입니다.  
  
### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>대화 상자가 아닌 창에서 ActiveX 컨트롤을 동적으로 생성 하려면  
  
1.  가변 원형 삽입 CMYVIEW에서 H입니다. H, 바로 앞의 `CMyView` 클래스 정의:  
  
     [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]  
  
2.  멤버 변수 추가 (형식의 `CCirc`)의 보호 된 섹션에는 `CMyView` 클래스 CMYVIEW에 정의 합니다. H:  
  
     [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]  
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]  
  
3.  추가 `WM_CREATE` 클래스에 메시지 처리기 `CMyView`합니다.  
  
4.  처리기 함수에서 `CMyView::OnCreate`, 컨트롤의 호출 `Create` 함수를 사용 하는 **이** 포인터 부모 창으로:  
  
     [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]  
  
5.  프로젝트를 다시 빌드합니다. Circ 컨트롤이 응용 프로그램의 뷰를 만들 때마다 동적으로 생성 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)

