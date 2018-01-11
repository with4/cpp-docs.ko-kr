---
title: "ABCFLOAT 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ABCFLOAT
dev_langs: C++
helpviewer_keywords: ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b58871df5a526455297dd6d092f98e9facd901ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="abcfloat-structure"></a>ABCFLOAT 구조체
`ABCFLOAT` 구조 A, B 및 C 너비 글꼴 문자가 포함 되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _ABCFLOAT { /* abcf */  
    FLOAT abcfA;  
    FLOAT abcfB;  
    FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *abcfA*  
 문자 A 간격을 지정 합니다. A 간격은 거리 문자 모양이 그리기 전에 현재 위치를 추가 합니다.  
  
 *abcfB*  
 문자의 B 간격을 지정 합니다. B 간격은 문자 모양이 그려지는 부분의 너비입니다.  
  
 *abcfC*  
 문자의 C 간격을 지정 합니다. C 간격은 문자 모양이의 오른쪽에 흰색 공간 제공 하기 위해 현재 위치에 추가할 거리를 설정 합니다.  
  
## <a name="remarks"></a>설명  
 A, B 및 C 폭 글꼴의 기준선을 따라 측정 됩니다. 문자 증가 (전체 너비)의 문자는 A, B 및 C 공간의 합계입니다. C 간격이 나 A underhangs 또는 돌출부 나타내기 위해 음수일 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

