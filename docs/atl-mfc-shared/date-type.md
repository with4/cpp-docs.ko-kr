---
title: "DATE 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: DATE
dev_langs: C++
helpviewer_keywords:
- Date data type, implementing
- Date data type
- DATE type
- Date data type, about Date data type
- MFC, date and time
- hour values representation
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f1ed7eb2b467fd52545f65f98b87e8e34ad71f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="date-type"></a>날짜 형식
**날짜** 형식이 8 바이트 부동 소수점 숫자를 사용 하 여 구현 됩니다. 일은 1899 년 12 월 30 일 자정 0 시로로 시작 하는 정수 증분으로 표시 됩니다. 시간 값은 숫자의 소수 부분의 절대값으로 표시 됩니다. 다음 표에서 여러 가지 날짜와 함께 설명의 **날짜** 형식 숫자 값:  
  
|날짜 및 시간|표현|  
|-------------------|--------------------|  
|1899 년 12 월 30 일 자정|0.00|  
|1 1900 년 1 월 자정|2.00|  
|4 1900 년 1 월 자정|5.00|  
|4 1900 년 1 월 오전 6 시|5.25|  
|1900 년 1 월 4 정오|5.50|  
|1900 월 4 일, 오후 9 시|5.875|  
  
 **날짜** 날짜 형식,으로 `COleDateTime` 클래스 클래식 번호 선으로 시간과 날짜를 나타냅니다. `COleDateTime` 클래스 기타 일반적인 날짜 형식 간의 변환을 포함 하 여 날짜 값을 조작 하기 위한 여러 메서드가 포함 되어 있습니다.  
  
 자동화에서 이러한 날짜 및 시간 형식으로 작업 하는 경우 다음 사항은 점에 유의 해야 합니다.  
  
-   현지 시간;에 지정 된 날짜 서로 다른 시간대에는 날짜와 함께 작업 하는 경우 동기화를 수동으로 수행 해야 합니다.  
  
-   날짜 형식 일광 절약 시간제에 고려 되지 않습니다.  
  
-   1899 년 12 월 30) (이전 날짜 시간 표시 막대 날짜 값의 0 보다 작은 비연속적 됩니다. 소수 부분이 처리 되는 동안 서명 된 date 값의 정수 부분이 처리 되기 때문에 이것이으로 합니다. 즉, 날짜 값의 소수 부분은 항상 전체 논리 날짜에 추가 하는 동안 양수 또는 음수 날짜 값의 정수 부분 수 있습니다. 다음 표에서 몇 가지 예를 보여 줍니다.  
  
|날짜 및 시간|표현|  
|-------------------|--------------------|  
|1899 년 12 월 27 일 자정|-3.00|  
|1899 년 12 월 28 정오|-2.50|  
|1899 년 12 월 28 일 자정|-2.00|  
|1899 년 12 월 29 일 자정|-1.00|  
|1899 년 12 월 30 일 오후 6 시|-0.75|  
|1899 년 12 월 30 정오|-0.50|  
|1899 년 12 월 30 일 오전 6 시|-0.25|  
|1899 년 12 월 30 일 자정|0.00|  
|1899 년 12 월 30 일 오전 6 시|0.25|  
|1899 년 12 월 30 정오|0.50|  
|1899 년 12 월 30 일 오후 6 시|0.75|  
|1899 년 12 월 31 일 자정|1.00|  
|1 1900 년 1 월 자정|2.00|  
|1900 년 1 월 1 정오|2.50|  
|2 1900 년 1 월 자정|3.00|  
  
> [!CAUTION]
>  오전 6시 항상 인지에 관계 없이 일을 나타내는 정수 양수 (1899 년 12 월 30 일) 이후 0.25 소수 값으로 표현 또는 1899 년 12 월 30 일) (이전 음수 이면 간단한 부동 지점 비교는 잘못 정렬 하기 때문에 note 모든 **날짜** 12/30/1899로 보다 이전 일 오전 6 시를 나타내는 *나중* 보다는 **날짜** 해당 같은 날 오전 7시 나타내는입니다.  
  
 와 관련 된 문제에 대 한 자세한 내용은 **날짜** 및 `COleDateTime` 형식을 확인할 수 있습니다 [COleDateTime 클래스](../atl-mfc-shared/reference/coledatetime-class.md) 및 [날짜 및 시간: 자동화 지원을](../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime 클래스](../atl-mfc-shared/reference/coledatetime-class.md)

