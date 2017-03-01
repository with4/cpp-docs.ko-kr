---
title: "LOGPEN 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
caps.latest.revision: 12
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
ms.openlocfilehash: f3868d2ac6a7b18cfe43f7da8865aed0a3ecf88d
ms.lasthandoff: 02/24/2017

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
  
- **PS_DASHDOT** 교대로 반복 되는 대시와 점이 가진 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- **PS_DASHDOTDOT** 교대로 반복 되는 대시와 이중 점이 가진 펜을 만듭니다. (경우에 유효 펜 너비는 1입니다.)  
  
- **PS_NULL** null 펜을 만듭니다.  
  
- **PS_INSIDEFRAME** 의 경계 사각형을 지정 하는 GDI 출력 함수를 통해 얻은 닫힌된 도형 프레임 내의 줄을 그리는 펜을 만듭니다 (예를 들어는 **타원**, **사각형**, `RoundRect`, `Pie`, 및 `Chord` 멤버 함수). GDI와이 스타일은 사용 하는 경우 출력 함수는 경계 사각형을 지정 하지 않은 (예를 들어는 `LineTo` 멤버 함수), 펜의 그리기 영역 프레임으로 제한 되지 않습니다.  
  
     펜 있으면는 **PS_INSIDEFRAME** 스타일과 논리 색상표에서 색이 일치 하지 않는 색 펜 디더링된 색으로 그려집니다. **PS_SOLID** 펜 스타일 디더링된 색으로 펜을 만드는 데 사용할 수 없습니다. **PS_INSIDEFRAME** 스타일은 동일 **PS_SOLID** 펜 굵기 1 보다 작은 경우.  
  
     때는 **PS_INSIDEFRAME** 스타일이 아닌 다른 함수를 통해 얻은 GDI 개체와 함께 사용 됩니다 **타원**, **사각형**, 및 `RoundRect`, 지정된 된 프레임 내 줄 완전히 되지 않을 수 있습니다.  
  
 *lopnWidth*  
 논리 단위에서 펜 굵기를 지정합니다. 하는 경우는 **lopnWidth** 멤버는 0, 태블릿 펜이 현재 매핑 모드에 관계 없이 래스터 장치에서 1 픽셀 너비입니다.  
  
 *lopnColor*  
 펜 색을 지정합니다.  
  
## <a name="remarks"></a>주의  
 **y** 값은 [지점](../../mfc/reference/point-structure1.md) 에 대 한 구조는 **lopnWidth** 멤버가 사용 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)


