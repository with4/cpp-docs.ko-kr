---
title: "RGNDATA 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4170b3590cc841f3edc10d4767045a4fede9782
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="rgndata-structure"></a>RGNDATA 구조체
`RGNDATA` 구조에는 헤더 및 영역을 구성 하는 사각형의 배열을 포함 합니다. 이러한 사각형 정렬된를 위에서 아래로 왼쪽에서 오른쪽으로 중첩 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rdh*  
 지정 된 [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) 구조입니다. (이 구조에 대 한 자세한 내용은 Windows SDK 참조). 이 구조체의 멤버 (여부는 사각형 또는 사다리꼴), 영역 직사각형 영역, 사각형 구조를 포함 하는 버퍼의 크기를 구성 하는 수의 유형을 지정 등에입니다.  
  
 `Buffer`  
 포함 된 임의의 크기 버퍼를 지정는 [RECT](../../mfc/reference/rect-structure1.md) 지역을 구성 하는 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

