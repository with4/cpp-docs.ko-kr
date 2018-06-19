---
title: LOGPEN 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure [MFC]
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c0e07ce3a38eaca54e860ebe821924c0f564c69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374152"
---
# <a name="logpen-structure"></a>LOGPEN 구조체
`LOGPEN` 그리기 개체를 그리는 데 사용 되는 선 및 테두리, 스타일, 두께 및 펜 색 구조를 정의 합니다. [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) 함수는 `LOGPEN` 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagLOGPEN {  /* lgpn */  
    UINT lopnStyle;  
    POINT lopnWidth;  
    COLORREF lopnColor;  
} LOGPEN;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *lopnStyle*  
 펜 유형을 지정합니다. 이 멤버는 다음 값 중 하나일 수 있습니다.  
  
- **PS_SOLID** 단색 펜을 만듭니다.  
  
- **PS_DASH** 파선된 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- **PS_DOT** 점선된 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- **PS_DASHDOT** 교대로 반복 되는 대시 및 점을 가진 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- **PS_DASHDOTDOT** 교대로 반복 되는 대시와 두 개의 점이 있는 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- **PS_NULL** null 펜을 만듭니다.  
  
- **PS_INSIDEFRAME** 줄의 경계 사각형을 지정 하는 GDI 출력 함수를 통해 얻은 프레임 내부를 그리는 펜을 만듭니다 (예를 들어는 **타원**, **사각형**, `RoundRect`, `Pie`, 및 `Chord` 멤버 함수). 경계 사각형을 지정 하지 않는 함수 출력 GDI와이 스타일은 사용 하는 경우 (예를 들어는 `LineTo` 멤버 함수), 펜의 그리기 영역 프레임으로 제한 되지 않습니다.  
  
     펜 있으면는 **PS_INSIDEFRAME** 스타일과 색 논리 색상표에서 색이 일치 하지 않는 펜 디더링된 색으로 그려집니다. **PS_SOLID** 펜 스타일을 디더링된 색 펜을 만드는 데 사용할 수 없습니다. **PS_INSIDEFRAME** 스타일은 동일 **PS_SOLID** 펜 굵기 1 보다 작은 경우.  
  
     경우는 **PS_INSIDEFRAME** 스타일은 아닌 다른 함수를 통해 얻은 GDI 개체와 사용 **타원**, **사각형**, 및 `RoundRect`, 줄 완전히 되지 않을 수 있습니다 지정된 된 프레임 내 합니다.  
  
 *lopnWidth*  
 논리 단위에서 펜 너비를 지정합니다. 경우는 **lopnWidth** 멤버는 0, 펜이 현재 매핑 모드에 관계 없이 래스터 장치에서 1 픽셀 너비입니다.  
  
 *lopnColor*  
 펜 색을 지정합니다.  
  
## <a name="remarks"></a>설명  
 **y** 값에 [지점](../../mfc/reference/point-structure1.md) 에 대 한 구조는 **lopnWidth** 멤버가 사용 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

