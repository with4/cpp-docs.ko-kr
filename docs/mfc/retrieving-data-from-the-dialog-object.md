---
title: "대화 상자 개체에서 데이터를 검색할 | Microsoft Docs"
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
- dialog boxes [MFC], retrieving user data
- dialog box data [MFC]
- data [MFC], retrieving
- GetDlgItemText method [MFC]
- SetDlgItemText method [MFC]
- SetWindowText method [MFC]
- dialog box data [MFC], retrieving
- retrieving data [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- dialog box controls [MFC], initializing values
- DDX (dialog data exchange) [MFC]
- MFC dialog boxes [MFC], retrieving user input
- data retrieval [MFC], dialog boxes
- data [MFC], dialog boxes
- DDX (dialog data exchange) [MFC], about DDX
- DDX (dialog data exchange) [MFC], retrieving data from Dialog object
- GetWindowText method [MFC]
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4b50ae3036a6f262312c7a05c2de093a977a588
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="retrieving-data-from-the-dialog-object"></a>대화 상자 개체에서 데이터 검색
프레임 워크 대화 상자에서 컨트롤의 값을 초기화 하 고 컨트롤에서 값을 검색 하는 쉬운 방법을 제공 합니다. 더 어려운 수동 방법은 같은 함수를 호출 하는 것은 `SetDlgItemText` 및 `GetDlgItemText` 클래스의 멤버 함수 `CWnd`, 제어 창을에 적용 되는 합니다. 이러한 함수를 사용 하면 액세스할 각 컨트롤을 개별적으로 설정 하거나 해당 값을 가져올와 같은 함수를 호출 `SetWindowText` 및 `GetWindowText`합니다. 프레임 워크의 접근 방식을 모두 초기화 및 검색을 자동화합니다.  
  
 대화 상자 데이터 교환 (DDX)를 사용 하면 대화 상자 개체에서 대화 상자와 멤버 변수에서 컨트롤 간에 데이터를 보다 쉽게 교환할 수 있습니다. 이 교환에는 두 가지 방식으로 작동 합니다. 대화 상자에서 컨트롤을 초기화 하려면 대화 상자 개체에서 데이터 멤버의 값을 설정할 수 있습니다 및 대화 상자가 표시 되기 전에 프레임 워크 컨트롤에 값 전송 됩니다. 다음 업데이트할 수 있습니다 언제 든 지 대화 상자 데이터 멤버는 사용자가 입력 한 데이터를 사용 합니다. 해당 시점에 데이터 멤버 변수를 참조 하 여 데이터를 사용할 수 있습니다.  
  
 대화 상자 데이터 유효성 검사 (DDV)와 함께 자동으로 유효성 검사 대화 상자 컨트롤의 값에 대 한 정렬할 수 있습니다.  
  
 DDX 및 DDV에서 더 자세하게에서 설명 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
 모달 대화 상자에 대 한 사용자가 입력 한 경우 모든 데이터를 검색할 수 있습니다 `DoModal` 반환 **IDOK** 하지만 개체가 소멸 되기 전에 대화 상자. 모덜리스 대화 상자를 검색할 수 있습니다 데이터 대화 상자 개체에서 언제 든 지 호출 하 여 `UpdateData` 인수와 함께 **TRUE** 하 고 다음 대화 상자 클래스 멤버 변수를 액세스 합니다. 이 주제에서 더 자세하게에서 설명 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

