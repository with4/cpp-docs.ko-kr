---
title: '경과 된 시간: 범용 클래스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating
- elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff7ef11bb20124a05e2e85c408ce27de8f982546
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354268"
---
# <a name="elapsed-time-general-purpose-classes"></a>경과 된 시간: 범용 클래스
다음 절차에는 두 개의 간의 차이 계산 하는 방법을 보여 줍니다 `CTime` 개체 및 get는 `CTimeSpan` 결과입니다.  
  
#### <a name="to-calculate-elapsed-time"></a>경과 시간을 계산 하려면  
  
1.  사용 하 여는 `CTime` 및 `CTimeSpan` 경과 시간을 다음과 같이 계산 하는 개체:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]  
  
     계산 했습니다 되 면 `elapsedTime`의 멤버 함수를 사용할 수 있습니다 `CTimeSpan` 경과 된 시간 값의 구성 요소를 추출 하 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간: 범용 클래스](../atl-mfc-shared/date-and-time-general-purpose-classes.md)

