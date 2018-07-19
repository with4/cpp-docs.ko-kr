---
title: LOGBRUSH 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure [MFC]
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15b904a07eb668a59a269741973424aa30e15877
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336408"
---
# <a name="logbrush-structure"></a>LOGBRUSH 구조체
`LOGBRUSH` 구조 스타일, 색 및 실제 브러시의 패턴을 정의 합니다. Windows에서 사용 됩니다 [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) 하 고 [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *lbStyle*  
 브러시 스타일을 지정합니다. `lbStyle` 멤버는 다음과 같은 스타일 중 하나 여야 합니다.  
  
- BS_DIBPATTERN 패턴 브러시 정의한 장치 독립적 비트맵을 (DIB) 사양입니다. 하는 경우 *lbStyle* BS_DIBPATTERN는 `lbHatch` 멤버 압축된 DIB에 대 한 핸들을 포함 합니다.  
  
- BS_DIBPATTERNPT 패턴 브러시 정의한 장치 독립적 비트맵을 (DIB) 사양입니다. 하는 경우 *lbStyle* BS_DIBPATTERNPT는 `lbHatch` 멤버 압축된 DIB에 대 한 포인터를 포함 합니다.  
  
- BS_HATCHED 무늬 브러시입니다.  
  
- 속이 빈 BS_HOLLOW 브러시입니다.  
  
- BS_NULL BS_HOLLOW 동일 합니다.  
  
- 메모리 비트맵을 정의한 BS_PATTERN 패턴 브러시입니다.  
  
- BS_SOLID 단색 브러시입니다.  
  
 *lbColor*  
 브러시를 그릴 수의 색을 지정 합니다. 하는 경우 *lbStyle* BS_HOLLOW 또는 BS_PATTERN 스타일이 *lbColor* 무시 됩니다. 경우 *lbStyle* BS_DIBPATTERN 인지 BS_DIBPATTERNBT의 하위 단어 *lbColor* 지정 여부를 `bmiColors` 의 멤버는 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) 구조 현재 표시 논리 팔레트에 명시적 빨강, 녹색, 파란색 (RGB) 값 또는 인덱스를 포함 합니다. `lbColor` 멤버는 다음 값 중 하나 여야 합니다.  
  
- 현재 표시 논리 팔레트에 16 비트 인덱스가 배열의 DIB_PAL_COLORS 색상표 구성 됩니다.  
  
- 색상표 DIB_RGB_COLORS 리터럴 RGB 값을 포함합니다.  
  
 *lbHatch*  
 빗살 무늬 스타일을 지정합니다. 의미를 통해 정의 된 브러시 스타일에 따라 달라 집니다 *lbStyle*합니다. 하는 경우 *lbStyle* BS_DIBPATTERN는 `lbHatch` 멤버 압축된 DIB에 대 한 핸들을 포함 합니다. 하는 경우 *lbStyle* BS_DIBPATTERNPT는 `lbHatch` 멤버 압축된 DIB에 대 한 포인터를 포함 합니다. 경우 *lbStyle* BS_HATCHED을가 `lbHatch` 멤버의 빗살 무늬를 만드는 데 줄의 방향을 지정 합니다. 다음 값 중 하나일 수 있습니다.  
  
- HS_BDIAGONAL는 45도 위쪽, 왼쪽에서 오른쪽 빗살 무늬  
  
- HS_CROSS 가로 및 세로 격자  
  
- HS_DIAGCROSS 45도 격자  
  
- HS_FDIAGONAL는 45 아래쪽, 왼쪽에서 오른쪽 빗살 무늬  
  
- 가로 HS_HORIZONTAL 빗살 무늬  
  
- 세로 HS_VERTICAL 빗살 무늬  
  
 경우 *lbStyle* BS_PATTERN, 됩니다 *lbHatch* 패턴을 정의 하는 비트맵 핸들입니다. 하는 경우 *lbStyle* BS_SOLID 인지, BS_HOLLOW *lbHatch* 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 하지만 *lbColor* 빗살 무늬 브러시의 전경색을 제어 합니다 [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) 하 고 [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) 배경 색을 제어 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

