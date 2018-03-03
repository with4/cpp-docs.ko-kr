---
title: "경과 된 시간: 범용 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51eea60669fb7ad35525d65013ffc8420649349b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="elapsed-time-general-purpose-classes"></a>경과 된 시간: 범용 클래스
다음 절차에는 두 개의 간의 차이 계산 하는 방법을 보여 줍니다 `CTime` 개체 및 get는 `CTimeSpan` 결과입니다.  
  
#### <a name="to-calculate-elapsed-time"></a>경과 시간을 계산 하려면  
  
1.  사용 하 여는 `CTime` 및 `CTimeSpan` 경과 시간을 다음과 같이 계산 하는 개체:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]  
  
     계산 했습니다 되 면 `elapsedTime`의 멤버 함수를 사용할 수 있습니다 `CTimeSpan` 경과 된 시간 값의 구성 요소를 추출 하 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간: 범용 클래스](../atl-mfc-shared/date-and-time-general-purpose-classes.md)

