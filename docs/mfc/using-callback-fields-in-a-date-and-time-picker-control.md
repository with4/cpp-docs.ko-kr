---
title: "콜백 필드를 사용 하 여 날짜 및 시간 선택 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e5526b0f8826a91eb0b1c5a6eae250abbb02fcf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤에서 콜백 필드 사용
날짜 및 시간 선택 필드를 정의 하는 표준 형식 문자 외에도 콜백 필드도 사용자 지정 형식 문자열의 특정 부분을 지정 하 여 출력을 사용자 지정할 수 있습니다. 콜백 필드를 선언 하려면 하나 이상의 "X" 문자 (ASCII 코드 88) 형식 문자열의 본문에서 아무 곳 이나 포함 합니다. 예를 들어 다음 문자열 "' 임: 'yy '/' MM '/' dd' (날 'X')'" 뒤에 월, 날짜 및 마지막 날짜의 연도와 현재 값을 표시 하려면 날짜 및 시간 선택 컨트롤 하면 됩니다.  
  
> [!NOTE]
>  수가 X 콜백 필드에 표시 되는 문자 수에 해당 하지 않습니다.  
  
 "X" 문자를 반복 하 여 사용자 지정 문자열의 여러 콜백 필드를 구분할 수 있습니다. 따라서 형식 문자열 "XXddddMMMdd', ' yyyXXX" "XX" 및 "XXX" 두 개의 고유한 콜백 필드를 포함 합니다.  
  
> [!NOTE]
>  콜백 필드는 응용 프로그램 처리를 준비 해야 하므로 유효한 필드가으로 처리 됩니다 **되므로 DTN_WMKEYDOWN** 알림 메시지입니다.  
  
 날짜 및 시간 선택 컨트롤에서 콜백 필드 구현 세 부분으로 구성 됩니다.  
  
-   사용자 지정 형식 문자열을 초기화  
  
-   처리는 **DTN_FORMATQUERY** 알림  
  
-   처리는 **DTN_FORMAT** 알림  
  
## <a name="initializing-the-custom-format-string"></a>사용자 지정 형식 문자열을 초기화  
 호출 하 여 사용자 지정 문자열을 초기화 `CDateTimeCtrl::SetFormat`합니다. 자세한 내용은 참조 [를 사용 하 여 사용자 지정 형식 문자열에서 날짜 및 시간 선택 컨트롤](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)합니다. 에 사용자 지정 형식 문자열을 설정 하는 일반적인 곳은 `OnInitDialog` 포함 하 여 대화 상자 클래스의 함수 또는 `OnInitialUpdate` 포함 된 뷰 클래스의 함수입니다.  
  
## <a name="handling-the-dtnformatquery-notification"></a>DTN_FORMATQUERY 알림 처리  
 컨트롤 형식 문자열을 구문 분석 하는 콜백 필드에서 발생 하는 경우 응용 프로그램 보냅니다 **DTN_FORMAT** 및 **DTN_FORMATQUERY** 알림 메시지입니다. 콜백 필드를 쿼리 하는 확인할 수 있도록 콜백 필드 문자열은 알림 메시지 내에 포함 됩니다.  
  
 **DTN_FORMATQUERY** 픽셀 현재 콜백 필드에 표시 되는 문자열의 최대 허용 크기를 검색 하 게 알림이 전송 됩니다.  
  
 이 값을 계산을 계산 해야 높이 너비는 필드에 대 한 대체 문자열의 컨트롤의 글꼴을 사용 하 여 합니다. 호출 하 여 문자열의 실제 계산 방법은 간단는 [GetTextExtentPoint32](http://msdn.microsoft.com/library/windows/desktop/dd144938) Win32 함수입니다. 크기 결정 되 면 값은 응용 프로그램에 다시 전달 하 고 처리기 함수를 종료 합니다.  
  
 다음 예제는 콜백 문자열의 크기를 제공 하는 한 가지 방법은:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]  
  
 계산 된 현재 콜백 필드의 크기 면 필드에 대 한 값을 제공 해야 합니다. 이 작업을 수행에 대 한 처리기는 **DTN_FORMAT** 알림입니다.  
  
## <a name="handling-the-dtnformat-notification"></a>DTN_FORMAT 알림 처리  
 **DTN_FORMAT** 알림 대체 되는 문자열을 요청 하는 응용 프로그램에서 사용 됩니다. 다음 예제에서는 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]  
  
> [!NOTE]
>  에 대 한 포인터는 **NMDATETIMEFORMAT** 적절 한 형식으로 알림 처리기의 첫 번째 매개 변수를 캐스팅 하 여 구조를 찾을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

