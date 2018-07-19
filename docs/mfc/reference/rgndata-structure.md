---
title: RGNDATA 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b775b14cb2f6b0f87bca1c81938c1a4c05c1304
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335671"
---
# <a name="rgndata-structure"></a>RGNDATA 구조체
`RGNDATA` 구조에는 헤더 및 영역을 구성 하는 사각형의 배열을 포함 합니다. 이러한 사각형 왼쪽에서 오른쪽으로 위에서 아래로 정렬 된 상위 겹치지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rdh*  
 지정 된 [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) 구조입니다. (이 구조에 대 한 자세한 내용은 Windows SDK 참조). 이 구조체의 멤버 영역 (사각형 또는 인지 사다리꼴), 영역, 사각형 구조를 포함 하는 버퍼의 크기를 구성 하는 사각형의 수 형식 지정 및 등입니다.  
  
 *Buffer*  
 포함 하는 임의 크기의 버퍼를 지정 합니다 [RECT](../../mfc/reference/rect-structure1.md) 지역을 구성 하는 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

