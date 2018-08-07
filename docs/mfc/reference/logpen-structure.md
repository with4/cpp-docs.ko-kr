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
ms.openlocfilehash: c677f86a44d24e0d0d2742d47ee1534532001528
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338534"
---
# <a name="logpen-structure"></a>LOGPEN 구조체
`LOGPEN` 구조 정의 스타일, 두께 및 펜의 색을 그리는 데 사용 되는 그리기 개체 선 및 테두리입니다. 합니다 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) 함수는 `LOGPEN` 구조입니다.  
  
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
 펜 형식을 지정합니다. 이 멤버는 다음 값 중 하나일 수 있습니다.  
  
- PS_SOLID solid 펜을 만듭니다.  
  
- PS_DASH 파선된 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- PS_DOT은 점으로 구분 된 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- PS_DASHDOT 교대로 반복 되는 펜을 대시 및 점을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- PS_DASHDOTDOT 대시 및 이중 점 교대로 반복 되는 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- PS_NULL null 펜을 만듭니다.  
  
- 경계 사각형을 지정 하는 함수 출력 PS_INSIDEFRAME 닫힌된 도형의 프레임 내에서 선을 그리는 펜을 생성 하 여 만듭니다 GDI (예를 들어 합니다 `Ellipse`, `Rectangle`를 `RoundRect`를 `Pie`, 및 `Chord` 멤버 함수)입니다. 경계 사각형을 지정 하지 않는 함수 출력 GDI를 사용 하 여이 스타일은 사용 하는 경우 (예를 들어를 `LineTo` 멤버 함수), 펜의 그리기 영역 프레임으로 제한 되지 않습니다.  
  
     펜 PS_INSIDEFRAME 스타일 및 색 논리 색상표에서 색을 일치 하지 않는 경우, 펜 디더링된 색으로 그려집니다. 디더링된 색을 사용 하 여 펜을을 만들려면 PS_SOLID 펜 스타일을 사용할 수 없습니다. PS_INSIDEFRAME 스타일은 1 보다 작거나 펜 굵기 이면 PS_SOLID 동일 합니다.  
  
     이외의 다른 함수에 의해 생성 된 PS_INSIDEFRAME 스타일 GDI 개체를 사용 하면 `Ellipse`, `Rectangle`, 및 `RoundRect`, 지정된 된 프레임 내에서 줄 완전히 되지 않을 수 있습니다.  
  
 *lopnWidth*  
 논리 단위의 펜 굵기를 지정합니다. 경우는 `lopnWidth` 구성원은 0, 펜은 현재 매핑 모드에 관계 없이 래스터 장치에서 1 픽셀 너비입니다.  
  
 *lopnColor*  
 펜의 색을 지정합니다.  
  
## <a name="remarks"></a>설명  
 합니다 `y` 값을 [지점](../../mfc/reference/point-structure1.md) 의 구조는 `lopnWidth` 멤버가 사용 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

