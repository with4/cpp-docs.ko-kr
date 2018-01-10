---
title: "날짜 및 시간: 자동화 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- formatting [Visual Studio], dates
- dates, Automation support
- elapsed time, calculating in Automation
- COleDateTime class, Automation date/time support
- COleDateTimeSpan class, Automation date/time support
- Automation, date and time support
- formatting [Visual Studio], time
- calculations, date and time
- time [Visual Studio], Automation support
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6a40a8fe49d9564714c328b657bc0d85d52ad84b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="date-and-time-automation-support"></a>날짜 및 시간: 자동화 지원
이 문서에서는 날짜 및 시간 관리와 관련 된 클래스 라이브러리 서비스를 활용 하는 방법을 설명 합니다. 설명 된 절차는 다음과 같습니다.  
  
-   [현재 시간 가져오기](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [경과 된 시간 계산](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [문자열 표현의 날짜/시간 형식 지정](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) 날짜 및 시간 정보를 나타내는 방법을 제공 합니다. 보다 세부적인 및 보다 큰 범위를 제공 된 [CTime](../atl-mfc-shared/reference/ctime-class.md) 클래스입니다. [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) 클래스 간 차이점과 같은 경과 된 시간을 나타냅니다. `COleDateTime` 개체입니다.  
  
 `COleDateTime` 및 `COleDateTimeSpan` 클래스 함께 사용할 수 있도록 고안 된는 `COleVariant` 자동화 하는 데 사용 합니다. `COleDateTime`및 `COleDateTimeSpan` 은 MFC 데이터베이스 프로그래밍에도 유용 하지만 날짜 및 시간 값을 조작 하려고 할 때마다 사용할 수 있습니다. 있지만 `COleDateTime` 클래스에는 더욱 광범위 한 값과 보다 세분화 된 `CTime` 클래스 보다 개체 당 더 많은 저장 있어야 `CTime`합니다. 또한 때 몇 가지 특별 한 내부 작업할 때 **날짜** 유형입니다. 참조 [DATE 형식](../atl-mfc-shared/date-type.md) 의 구현에 대 한 자세한 내용은 **날짜**합니다.  
  
 `COleDateTime`날짜를 나타내는 100 년 1 월 1 일, 년 12 월 31 일 사이 9999 개체를 사용할 수 있습니다. `COleDateTime`개체에 부동 소수점 값 1 밀리초의 대략적인 해상도와 됩니다. `COleDateTime`에 따라는 **날짜** 에서 MFC 설명서에 정의 된 데이터 형식, [COleDateTime::operator 날짜](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)합니다. 실제 구현 **날짜** 이러한 범위를 벗어났습니다. `COleDateTime` 구현 클래스와 작업을 용이 하 게 하려면 이러한 경계를 적용 합니다.  
  
 `COleDateTime`율리우스력 날짜를 지원 하지 않습니다. 일반 달력 시간에서 100 년 1 월 1 일에 확장으로 간주 됩니다.  
  
 `COleDateTime`일광 절약 시간제 DST ()를 무시합니다. 다음 코드 예제에서는 시간 범위 전환 날짜를 계산 하는 두 가지 방법을 비교:는 CRT를 사용 하 여 하나 및 다른 using `COleDateTime`합니다. DST 전환, 대부분의 로캘에서에서 두 번째 주 4 월에서 및 10 월에 세 번째 합니다.  
  
 두 개의 설정 하는 첫 번째 방법은 `CTime` 개체 *time1* 및 *time2*, 5 년 4 월 및 4 월 6 각각 표준 C 형식 구조를 사용 하 여 **tm** 및 `time_t`. 코드 표시 *time1* 및 *time2* 및 서로 시간 범위입니다.  
  
 두 번째 방법에서는 두 개의 `COleDateTime` 개체 `oletime1` 및 `oletime2`, 동일한 날짜를 설정 하 고 *time1* 및 *time2*합니다. 표시 `oletime1` 및 `oletime2` 및 서로 시간 범위입니다.  
  
 CRT는 올바르게 23 시간 차이 계산합니다. `COleDateTimeSpan`24 시간 차이 계산합니다.  
  
 올바르게 사용 하 여 날짜를 표시 하는 해결 방법 예제의 끝 부분에서 사용 됩니다 `COleDateTime::Format`합니다. 기술 자료 문서 "버그: Format("%D")에 대 한 실패 `COleDateTime` 및 `COleDateTimeSpan`" (Q167338).  
  
 [!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간](../atl-mfc-shared/date-and-time.md)

