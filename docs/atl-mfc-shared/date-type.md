---
title: "DATE Type | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "DATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Date 데이터 형식"
  - "Date 데이터 형식, about Date data type"
  - "Date 데이터 형식, 구현"
  - "DATE type"
  - "hour values representation"
  - "MFC, 날짜 및 시간"
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DATE Type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**날짜** 형식은 8 바이트 부동 소수점 숫자를 사용 하 여 구현 됩니다.  일 1899 년 12 월 30 일 자정 시간 0으로 시작 하는 숫자 씩 표시 됩니다.  시간 값은 숫자의 소수 부분의 절대값으로 표시 됩니다.  함께 몇 가지 날짜 다음 표에 나와 자신의  **날짜** 해당 숫자 형식:  
  
|날짜 및 시간|표현|  
|-------------|--------|  
|1899 년 12 월 30 일 자정|0.00|  
|1 1900 년 1 월 자정|2.00|  
|4 1900 년 1 월 자정|5.00|  
|4 1900 년 1 월 6 A.M.|5.25|  
|4 1900 년 1 월 정오|5.50|  
|4 1900 년 1 월 9 P.M.|5.875|  
  
 **날짜** 날짜 형식으로 `COleDateTime` 클래스에서 나타내는 날짜 및 시간과 클래식 수 선으로.  `COleDateTime` 클래스에는 다른 일반적인 날짜 형식 변환을 비롯 하 여 날짜 값을 조작 하기 위한 여러 가지 방법을 포함 합니다.  
  
 이러한 자동화의 날짜 및 시간 형식으로 작업할 때 다음 사항은 유의 해야:  
  
-   날짜 현지 시간으로 지정 됩니다. 서로 다른 표준 시간대의 날짜와 함께 작업 하는 경우 동기화를 수동으로 수행 되어야 합니다.  
  
-   날짜 형식에 대 한 일광 절약 시간제 고려 되지 않습니다.  
  
-   날짜 시간 표시 막대 0 보다 작은 경우 날짜 값에 대 한 불연속 \(30 1899 년 12 월 이전\)가 됩니다.  정수 부분은 날짜 값의 소수 부분을 처리 하는 동안 서명 된 값으로 처리 됩니다 때문입니다 부호 없는 값으로.  즉, 날짜 값의 소수 부분이 항상 전체 논리 날짜를 추가 하는 동안 날짜 값의 정수 부분 양수 또는 음수일 수 있습니다.  다음 표에서 몇 가지 예제를 보여 줍니다.  
  
|날짜 및 시간|표현|  
|-------------|--------|  
|1899 년 12 월 27 일 자정|\-3.00|  
|1899 년 12 월 28, 정오|\-2.50|  
|1899 년 12 월 28 일 자정|\-2.00|  
|1899 년 12 월 29 일 자정|\-1.00|  
|1899 년 12 월 30 일 6 P.M.|\-0.75|  
|1899 년 12 월 30, 정오|\-0.50|  
|1899 년 12 월 30 일 6 A.M.|\-0.25|  
|1899 년 12 월 30 일 자정|0.00|  
|1899 년 12 월 30 일 6 A.M.|0.25|  
|1899 년 12 월 30, 정오|0.50|  
|1899 년 12 월 30 일 6 P.M.|0.75|  
|1899 년 12 월 31 일 자정|1.00|  
|1 1900 년 1 월 자정|2.00|  
|1900 년 1 월 정오|2.50|  
|2 1900 년 1 월 자정|3.00|  
  
> [!CAUTION]
>  오전 6 시 소수 값 0.25 일을 나타내는 정수 \(30, 1899 년 12 월 이후\) 양수 여부에 관계 없이 항상 표시 또는 음수 \(1899 년 12 월 30 일\) 전에 간단한 부동 소수점 비교 됩니다 잘못 때문에 정렬할 참고  **날짜** 오전 6 시에서 1899 년 12 월 30 일으로 보다 이전 날짜를 나타내는  *나중에* 보다는  **날짜** 는 같은 날 오전 7시 나타내는.  
  
 와 관련 된 문제에 대 한 자세한 내용은  **날짜** 및 `COleDateTime` 유형 아래에서 찾을 수 있습니다 [COleDateTime Class](../atl-mfc-shared/reference/coledatetime-class.md) 및 [Date and Time: Automation Support](../atl-mfc-shared/date-and-time-automation-support.md).  
  
## 참고 항목  
 [Date and Time](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime Class](../atl-mfc-shared/reference/coledatetime-class.md)