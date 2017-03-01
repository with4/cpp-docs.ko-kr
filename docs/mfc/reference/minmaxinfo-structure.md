---
title: "MINMAXINFO 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 772416bdac3c72f55644fa31aef23ba76a14e606
ms.lasthandoff: 02/24/2017

---
# <a name="minmaxinfo-structure"></a>MINMAXINFO 구조체
`MINMAXINFO` 구조 창 최대화 된 크기와 위치 및 추적 최소 및 최대 크기에 대 한 정보를 포함 합니다.  
  
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
 최대화 된 너비 (point.x) 및 창 최대화 높이 (point.y)를 지정합니다.  
  
 `ptMaxPosition`  
 최대화 된 창 (point.x)의 왼쪽의 위치와 맨 위에 있는 최대화 된 창 (point.y)의 위치를 지정합니다.  
  
 *ptMinTrackSize*  
 최소 추적 너비 (point.x) 및 최소 추적 창의 높이 (point.y)를 지정 합니다.  
  
 *ptMaxTrackSize*  
 최대 너비 (point.x)을 추적 및 추적 창의 높이 (point.y) 최대 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)


