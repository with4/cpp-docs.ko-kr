---
title: "다중 스레드 라이브러리 성능 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], performance
- libraries, multithreaded
- performance, multithreading
- multithreaded libraries
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b2a6f6535092043fe2f32c08fbb522ff3c367063
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="multithreaded-libraries-performance"></a>다중 스레드 라이브러리 성능
단일 스레드 CRT는 더 이상 사용할 수 없습니다. 이 항목에서는 다중 스레드 라이브러리에서 최대 성능을 얻는 방법에 대해 설명합니다.  
  
## <a name="maximizing-performance"></a>성능 극대화  
 다중 스레드 라이브러리의 성능이 개선되어 지금은 제거된 단일 스레드 라이브러리의 성능에 근접하게 되었습니다. 더 높은 성능이 필요한 경우를 위해 여러 가지 새로운 기능이 추가되었습니다.  
  
-   독립적인 스트림 잠금 기능을 통해 스트림을 잠근 다음 스트림에 직접 액세스하는 [_nolock 함수](../c-runtime-library/nolock-functions.md)를 사용할 수 있습니다. 이로 인해 중요한 루프 외부에서 잠금 사용을 해제할 수 있습니다.  
  
-   스레드별 로캘은 다중 스레드 시나리오에 대해 로캘 액세스 비용을 줄여 줍니다([_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 참조).  
  
-   로캘 종속 함수(이름이 _l로 끝남)는 로캘을 매개 변수로 사용하여 비용을 상당히 절감합니다(예: [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)).  
  
-   공통 코드 페이지에 대한 최적화는 많은 짧은 작업의 비용을 절감합니다.  
  
-   [_CRT_DISABLE_PERFCRIT_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md)를 정의하면 모든 I/O 작업이 단일 스레드 I/O 모델을 가정하고 함수의 _nolock 형태를 사용하게 됩니다. 이로 인해 상당히 I/O를 기반으로 하는 단일 스레드 응용 프로그램의 성능이 향상됩니다.  
  
-   CRT 힙 핸들을 노출하면 CRT 힙에 대해 Windows LFH(낮은 조각화 힙)가 가능해져 규모가 큰 시나리오에서 성능이 상당히 개선될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)
