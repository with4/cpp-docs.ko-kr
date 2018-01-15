---
title: "사용자 지정 형식 문자열을 사용 하 여 날짜 및 시간 선택 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bfaad06571a8648db24497c46d55cb2eb1ce2157
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤에서 사용자 지정 서식 문자열 사용
기본적으로 날짜 및 시간 선택 컨트롤 세 가지의 형식 (각 형식에 해당 하는 고유 스타일) 현재 날짜 또는 시간을 표시 하기 위한 형식을 제공 합니다.  
  
-   **DTS_LONGDATEFORMAT** "년 1 월 3 2000 일 수요일"와 같은 출력을 생성 하는 긴 형식으로 날짜를 표시 합니다.  
  
-   **DTS_SHORTDATEFORMAT** "1/3/00"와 같은 출력을 생성 하는 short 형식으로 날짜를 표시 합니다.  
  
-   **DTS_TIMEFORMAT** "오후 5시 31분: 42"와 같은 출력을 생성 하는 긴 형식으로 시간을 표시 합니다.  
  
 그러나 사용자 지정 형식 문자열을 사용 하 여 날짜 또는 시간의 모양을 사용자 지정할 수 있습니다. 이 사용자 지정 문자열 기존 서식 문자, 비 문자 또는 둘의 조합으로 이루어져 있습니다. 사용자 지정 문자열 작성 된 후 확인에 대 한 호출 [CDateTimeCtrl::SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) 사용자 지정 문자열에 전달 합니다. 다음 날짜 및 시간 선택 컨트롤 사용자 지정 형식 문자열을 사용 하 여 현재 값이 표시 됩니다.  
  
 다음 예제 코드 (여기서 `m_dtPicker` 는 `CDateTimeCtrl` 개체) 한 가지 가능한 해결 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 사용자 지정 형식 문자열 외에도 날짜 및 시간 선택도 지 원하는 컨트롤 [콜백 필드](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

