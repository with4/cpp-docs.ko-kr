---
title: "LOGBRUSH 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: eea7caf6139fd43dd77163271701d170c7a744e2
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="logbrush-structure"></a>LOGBRUSH 구조체
`LOGBRUSH` 구조 스타일, 색 및 실제 브러시의 패턴을 정의 합니다. Windows에서 사용 되는 [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) 및 [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lbStyle`  
 브러시 스타일을 지정합니다. `lbStyle` 멤버는 다음과 같은 스타일 중 하나 여야 합니다.  
  
- **BS_DIBPATTERN** 장치 독립적 비트맵 (DIB) 사양에 정의 된 패턴 브러시입니다. 경우 `lbStyle` 는 **BS_DIBPATTERN**, **lbHatch** 멤버 압축된 DIB에 대 한 핸들을 포함 합니다.  
  
- **BS_DIBPATTERNPT** 장치 독립적 비트맵 (DIB) 사양에 정의 된 패턴 브러시입니다. 경우 `lbStyle` 는 **BS_DIBPATTERNPT**, **lbHatch** 멤버 압축된 DIB에 대 한 포인터를 포함 합니다.  
  
- **BS_HATCHED** 무늬 브러시입니다.  
  
- **BS_HOLLOW** 브러시 흰색입니다.  
  
- **BS_NULL** 동일 **BS_HOLLOW**합니다.  
  
- **BS_PATTERN** 브러시 메모리 비트맵에 정의 된 패턴입니다.  
  
- **BS_SOLID** 단색 브러시입니다.  
  
 `lbColor`  
 브러시를 그릴의 색을 지정 합니다. 경우 `lbStyle` 는 **BS_HOLLOW** 또는 **BS_PATTERN** 스타일 **lbColor** 무시 됩니다. 경우 `lbStyle` 는 **BS_DIBPATTERN** 또는 **BS_DIBPATTERNBT**의 하위 단어로 **lbColor** 지정 여부는 **bmiColors** 의 멤버는 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) 현재 실현된 논리 색상표에 명시적 빨간색, 녹색, 파란색 (RGB) 값 또는 인덱스를 포함 하는 구조입니다. **lbColor** 멤버는 다음 값 중 하나 여야 합니다.  
  
- **DIB_PAL_COLORS** 현재 실현된 논리 색상표를 색상표 16 비트 인덱스 배열의으로 구성 됩니다.  
  
- **DIB_RGB_COLORS** 색상표 리터럴 RGB 값을 포함 합니다.  
  
 *lbHatch*  
 해치 스타일을 지정합니다. 의미에 정의 된 브러시 스타일에 따라 달라 집니다 `lbStyle`합니다. 경우 `lbStyle` 는 **BS_DIBPATTERN**, **lbHatch** 멤버 압축된 DIB에 대 한 핸들을 포함 합니다. 경우 `lbStyle` 는 **BS_DIBPATTERNPT**, **lbHatch** 멤버 압축된 DIB에 대 한 포인터를 포함 합니다. 경우 `lbStyle` 는 **BS_HATCHED**, **lbHatch** 멤버를 만드는 해치는 사용 되는 줄의 방향을 지정 합니다. 다음 값 중 하나일 수 있습니다.  
  
- `HS_BDIAGONAL`45도 위쪽, 왼쪽에서 오른쪽 빗살 무늬  
  
- `HS_CROSS`가로 및 세로 격자  
  
- `HS_DIAGCROSS`45도 격자  
  
- `HS_FDIAGONAL`45도 아래쪽, 왼쪽에서 오른쪽 빗살 무늬  
  
- `HS_HORIZONTAL`가로 빗살 무늬  
  
- `HS_VERTICAL`세로 빗살 무늬  
  
 경우 `lbStyle` 는 **BS_PATTERN**, **lbHatch** 패턴을 정의 하는 비트맵에 대 한 핸들입니다. 경우 `lbStyle` 는 **BS_SOLID** 또는 **BS_HOLLOW**, **lbHatch** 무시 됩니다.  
  
## <a name="remarks"></a>주의  
 하지만 **lbColor** 빗금 브러시의 전경 색을 제어는 [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) 및 [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) 배경 색을 제어 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


