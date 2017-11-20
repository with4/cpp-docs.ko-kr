---
title: "RECT 구조 1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs: C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d3a33330ace97db19521362384356b58a6c8dca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="rect-structure1"></a>RECT 구조 1
`RECT` 구조체는 사각형의 왼쪽 위 및 오른쪽 아래 모퉁이의 좌표를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>멤버  
 `left`  
 사각형의 왼쪽 위 모퉁이의 x좌표를 지정합니다.  
  
 `top`  
 사각형의 왼쪽 위 모퉁이의 y좌표를 지정합니다.  
  
 `right`  
 사각형의 오른쪽 아래 모퉁이의 x좌표를 지정합니다.  
  
 `bottom`  
 사각형의 오른쪽 아래 모퉁이의 y좌표를 지정합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** windef.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect 클래스](../../atl-mfc-shared/reference/crect-class.md)
