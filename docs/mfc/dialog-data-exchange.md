---
title: 대화 상자 데이터 교환 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing dialog boxes
- canceling data exchange
- dialog box data, retrieving
- DDX (dialog data exchange), data exchange mechanism
- dialog boxes [MFC], initializing
- dialog boxes [MFC], retrieving user input using DDX
- dialog box data
- dialog boxes [MFC], data exchange
- CDataExchange class [MFC], using DDX
- DoDataExchange method [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- transferring dialog box data
- DDX (dialog data exchange), canceling
- UpdateData method [MFC]
- retrieving dialog box data [MFC]
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2385efcef9949eab60b1542b2039e3ff2ac80e38
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930861"
---
# <a name="dialog-data-exchange"></a>대화 상자 데이터 교환
DDX 메커니즘을 사용 하는 경우 대화 상자의 초기 값 개체의 멤버 변수를 설정 하면 일반적으로 프로그램 `OnInitDialog` 처리기 또는 대화 생성자입니다. 프레임 워크의 DDX 메커니즘 표시 되는 위치 대화 상자에서 컨트롤을 멤버 변수의 값을 전송 대화 상자가 표시 되기 전에 즉시 자체 대화 상자가 표시 되 면 대 한 응답으로 `DoModal` 또는 `Create`합니다. 기본 구현은 `OnInitDialog` 에 `CDialog` 호출은 `UpdateData` 클래스의 멤버 함수 `CWnd` 대화 상자에서 컨트롤을 초기화 합니다.  
  
 동일한 메커니즘 값에서에서 전송 컨트롤 멤버 변수 확인 단추를 클릭할 때 (호출할 때마다 또는 `UpdateData` 멤버 함수는 인수를 **TRUE**). 대화 상자 데이터 유효성 검사 메커니즘은 유효성 검사 규칙을 지정한 데이터 항목의 유효성을 검사 합니다.  
  
 다음 그림은 대화 상자 데이터 교환 합니다.  
  
 ![대화 상자 데이터 교환](../mfc/media/vc379d1.gif "vc379d1")  
대화 상자 데이터 교환  
  
 `UpdateData` 에 지정 된 대로 두 방향에서 작동 하는 **BOOL** 매개 변수를 전달 합니다. Exchange를 수행 하려면 `UpdateData` 를 설정는 `CDataExchange` 대화 상자 클래스의 개체 및 호출의 재정의 `CDialog`의 `DoDataExchange` 멤버 함수입니다. `DoDataExchange` 형식의 인수를 사용 `CDataExchange`합니다. `CDataExchange` 에 전달 된 개체 `UpdateData` 교환의 방향으로 이러한 정보를 정의 교환의 컨텍스트를 나타냅니다.  
  
 사용자 (또는 코드 마법사) 재정의 하는 경우 `DoDataExchange`, 데이터 멤버 (컨트롤) 당 하나의 DDX 함수에 대 한 호출을 지정 합니다. 각 DDX 함수 양방향 제공한 컨텍스트를 기반으로 데이터를 교환 하는 방법을 알고는 `CDataExchange` 인수에 전달 된 프로그램 `DoDataExchange` 여 `UpdateData`합니다.  
  
 MFC는 서로 다른 exchange에 대 한 다양 한 DDX 함수를 제공합니다. 다음 예제와 `DoDataExchange` 재정의 두 개의 DDX 함수 및 DDV 함수가 두 개 이라고 합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]  
  
 `DDX_` 및 `DDV_` 선은 데이터 맵을 합니다. 표시 되는 샘플 DDX 및 DDV 함수는 확인란 컨트롤과 편집 상자 컨트롤에 대 한 각각입니다.  
  
 모달 대화 상자를 취소 하는 경우는 `OnCancel` 대화 상자를 종료 하는 멤버 함수 및 `DoModal` 값을 반환 **IDCANCEL**합니다. 이 경우 데이터가 없는 대화 상자 및 대화 상자 개체 간에 교환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [대화 상자 데이터 유효성 검사](../mfc/dialog-data-validation.md)

