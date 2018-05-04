---
title: '자동화 클래스: | Microsoft Docs'
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
- elapsed time, calculating in Automation
- Automation classes, elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1abf6274137ae67b159ad43612d24020a0d14e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="elapsed-time-automation-classes"></a>경과 된 시간: 자동화 클래스
이 절차에서는 두 개의 간의 차이 계산 하는 방법을 보여 줍니다. `CTime` 개체 및 get는 `CTimeSpan` 결과입니다.  
  
#### <a name="to-calculate-elapsed-time"></a>경과 시간을 계산 하려면  
  
1.  두 개 만든 `COleDateTime` 개체입니다.  
  
2.  설정 중 하나는 `COleDateTime` 을 현재 시간 개체입니다.  
  
3.  시간이 많이 걸리는 작업을 수행 합니다.  
  
4.  다른 설정 `COleDateTime` 개체는 현재 시간입니다.  
  
5.  두 시간 사이의 차이 고려 합니다.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간: 자동화 지원](../atl-mfc-shared/date-and-time-automation-support.md)

