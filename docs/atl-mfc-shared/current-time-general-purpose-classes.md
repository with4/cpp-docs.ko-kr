---
title: "현재 시간: 일반 용도의 클래스 | Microsoft Docs"
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
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6c43ffd60d837bdd8f061057cf1c36340b6e6af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="current-time-general-purpose-classes"></a>현재 시간: 범용 클래스
다음 절차를 만드는 방법을 보여는 `CTime` 개체를 현재 시간으로 초기화 합니다.  
  
#### <a name="to-get-the-current-time"></a>현재 시간을 가져옵니다.  
  
1.  할당 한 `CTime` 다음과 같이 개체:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  초기화 되지 않은 `CTime` 개체 요소가 올바른 시간으로 초기화 되지 않았습니다.  
  
2.  호출 된 `CTime::GetCurrentTime` 함수를 운영 체제에서 현재 시간을 가져옵니다. 이 함수는 반환 된 `CTime` 개체의 값을 설정 하는 데 사용할 수 있는 `CTime`다음과 같이:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]  
  
     이후 `GetCurrentTime` 에서 정적 멤버 함수는 `CTime` 클래스 이름 클래스 및 범위 결정 연산자를 사용 하 여 이름을 정규화 해야 (`::`), `CTime::GetCurrentTime()`합니다.  
  
 물론, 위에서 설명한 두 단계 이전에 결합 결합할 수 있습니다 프로그램 단일 문으로 다음과 같습니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간: 범용 클래스](../atl-mfc-shared/date-and-time-general-purpose-classes.md)



