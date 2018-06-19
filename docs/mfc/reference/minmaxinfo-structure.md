---
title: MINMAXINFO 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12161938f96e5044ae48f9eb5cf380fbc3840d3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369520"
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO 구조체
`MINMAXINFO` 구조 창 최대화 크기와 위치 및 최소 및 최대 추적 크기에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagMINMAXINFO {  
    POINT ptReserved;  
    POINT ptMaxSize;  
    POINT ptMaxPosition;  
    POINT ptMinTrackSize;  
    POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *ptReserved*  
 내부용으로 예약됩니다.  
  
 *ptMaxSize*  
 최대화 된 상태로 너비 (point.x) 및 창 최대화 높이 (point.y)를 지정합니다.  
  
 `ptMaxPosition`  
 (Point.y) 최대화 된 창의 위쪽의 위치와 최대화 창 (point.x)의 왼쪽의 위치를 지정합니다.  
  
 *ptMinTrackSize*  
 최소 추적 너비 (point.x) 및 최소 추적 창의 높이 (point.y)를 지정 합니다.  
  
 *ptMaxTrackSize*  
 최대 너비 (point.x)를 추적 하 고 최대 창 높이 (point.y)를 추적을 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

