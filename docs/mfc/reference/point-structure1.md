---
title: "지점 구조&1; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- POINT
- LPPOINT
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: d1e2bb05f9bad785b13e79413866d8e0ce1e1faa
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="point-structure1"></a>지점 구조&1;
**가리킨** 구조 정의 x* - * , 점의 y 좌표입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagPOINT {  
    LONG x;  
    LONG y;  
} POINT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *x*  
 점의 x 좌표를 지정합니다.  
  
 *y*  
 점의 y 좌표를 지정합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities #&37;](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** windef.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint 클래스](../../atl-mfc-shared/reference/cpoint-class.md)

