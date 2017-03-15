---
title: "RECT 구조&1; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure
- LPRECT structure
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: 13
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: bc91b22f291f23ed396a054b0c929410718286a3
ms.lasthandoff: 02/24/2017

---
# <a name="rect-structure1"></a>RECT 구조&1;
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
 [!code-cpp[NVC_MFC_Utilities #&38;](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** windef.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect 클래스](../../atl-mfc-shared/reference/crect-class.md)

