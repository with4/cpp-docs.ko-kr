---
title: "LOGBRUSH 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LOGBRUSH
dev_langs: C++
helpviewer_keywords: LOGBRUSH structure [MFC]
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec6cc9b61f837db4c9766c077fa60f4d9c2b95bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="logbrush-structure"></a>LOGBRUSH 구조체
`LOGBRUSH` 구조 스타일, 색 및 실제 브러시의 패턴을 정의 합니다. Windows에서 사용 되 고 [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) 및 [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) 함수입니다.  
  
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
  
- **BS_DIBPATTERN** 장치 독립적 비트맵 (DIB) 사양에 정의 된 패턴 브러시입니다. 경우 `lbStyle` 은 **BS_DIBPATTERN**, **lbHatch** 멤버 압축된 DIB에 대 한 핸들을 포함 합니다.  
  
- **BS_DIBPATTERNPT** 장치 독립적 비트맵 (DIB) 사양에 정의 된 패턴 브러시입니다. 경우 `lbStyle` 은 **BS_DIBPATTERNPT**, **lbHatch** 멤버 압축된 DIB에 대 한 포인터를 포함 합니다.  
  
- **BS_HATCHED** 무늬 브러시입니다.  
  
- **BS_HOLLOW** 브러시 흰색입니다.  
  
- **BS_NULL** 동일 **BS_HOLLOW**합니다.  
  
- **BS_PATTERN** 브러시 메모리 비트맵에 정의 된 패턴을 사용 합니다.  
  
- **BS_SOLID** 단색 브러시입니다.  
  
 `lbColor`  
 브러시를 그리지 않아도 색을 지정 합니다. 경우 `lbStyle` 는 **BS_HOLLOW** 또는 **BS_PATTERN** 스타일 **lbColor** 는 무시 됩니다. 경우 `lbStyle` 은 **BS_DIBPATTERN** 또는 **BS_DIBPATTERNBT**의 하위 단어 **lbColor** 지정 여부는 **bmiColors**의 멤버는 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) 현재 실현된 논리 팔레트에 명시적 빨강, 녹색, 파란색 (RGB) 값 또는 인덱스를 포함 하는 구조입니다. **lbColor** 멤버는 다음 값 중 하나 여야 합니다.  
  
- **DIB_PAL_COLORS** 현재 실현된 논리 팔레트를 색상표 16 비트 인덱스의 배열으로 구성 됩니다.  
  
- **DIB_RGB_COLORS** 색상표 리터럴 RGB 값을 포함 합니다.  
  
 *lbHatch*  
 해치 스타일을 지정합니다. 의미에 정의 된 브러시 스타일에 따라 다릅니다. `lbStyle`합니다. 경우 `lbStyle` 은 **BS_DIBPATTERN**, **lbHatch** 멤버 압축된 DIB에 대 한 핸들을 포함 합니다. 경우 `lbStyle` 은 **BS_DIBPATTERNPT**, **lbHatch** 멤버 압축된 DIB에 대 한 포인터를 포함 합니다. 경우 `lbStyle` 은 **BS_HATCHED**, **lbHatch** 멤버는 해치를 만드는 데 줄의 방향을 지정 합니다. 다음 값 중 하나일 수 있습니다.  
  
- `HS_BDIAGONAL`45도 위쪽, 왼쪽에서 오른쪽 빗살 무늬  
  
- `HS_CROSS`가로 및 세로 격자  
  
- `HS_DIAGCROSS`45도 격자  
  
- `HS_FDIAGONAL`45도 아래쪽, 왼쪽에서 오른쪽 빗살 무늬  
  
- `HS_HORIZONTAL`가로 빗살 무늬  
  
- `HS_VERTICAL`세로 빗살 무늬  
  
 경우 `lbStyle` 은 **BS_PATTERN**, **lbHatch** 는 패턴을 정의 하는 비트맵에 대 한 핸들입니다. 경우 `lbStyle` 은 **BS_SOLID** 또는 **BS_HOLLOW**, **lbHatch** 는 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 하지만 **lbColor** 빗살 무늬 브러시의 전경색을 제어는 [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) 및 [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) 배경 색을 제어 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

