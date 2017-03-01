---
title: "RGNDATA 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
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
ms.openlocfilehash: 93a7c79f175e22dcb0b40cb39b157cfe21a98e93
ms.lasthandoff: 02/24/2017

---
# <a name="rgndata-structure"></a>RGNDATA 구조체
`RGNDATA` 구조는 헤더 및 영역을 구성 하는 사각형의 배열을 포함 합니다. 이 사각형을 정렬된 하 여 위에서 아래로 왼쪽에서 오른쪽으로 중첩 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rdh*  
 지정 된 [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) 구조입니다. (이 구조에 대 한 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].) 이 구조체의 멤버는 영역의 형식을 (사각형 또는 인지 사다리꼴), 영역, 사각형 구조를 포함 하는 버퍼의 크기를 구성 하는 사각형의 수를 지정 하 고 등.  
  
 `Buffer`  
 포함 하는 임의 크기의 버퍼를 지정 합니다.는 [RECT](../../mfc/reference/rect-structure1.md) 지역을 구성 하는 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)


