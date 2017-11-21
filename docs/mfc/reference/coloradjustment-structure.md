---
title: "COLORADJUSTMENT 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLORADJUSTMENT
dev_langs: C++
helpviewer_keywords: COLORADJUSTMENT structure [MFC]
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5c5f99cbd94ffc1a5549367d8f21ad15a9398acb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT 구조체
`COLORADJUSTMENT` 구조 정의 Windows에서 사용 되는 색 조정 값 `StretchBlt` 및 **StretchDIBits** 함수 때는 `StretchBlt` 모드는 **하프톤**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD caSize;  
    WORD caFlags;  
    WORD caIlluminantIndex;  
    WORD caRedGamma;  
    WORD caGreenGamma;  
    WORD caBlueGamma;  
    WORD caReferenceBlack;  
    WORD caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *caSize*  
 구조체의 크기를 바이트 단위로 지정 합니다.  
  
 *caFlags*  
 출력 이미지를 준비 하는 방식을 지정 합니다. 이 멤버는로 설정할 수 있습니다 **NULL** 또는 다음 값을 조합 합니다.  
  
- **CA_NEGATIVE** 원본 이미지의 음수를 표시 하도록 지정 합니다.  
  
- **CA_LOG_FILTER** 출력 색의 최종 밀도에 로그 함수를 적용 해야 하는지 지정 합니다. 이렇게 하면 광도 부족할 때 색상 대비를 늘어납니다.  
  
 *caIlluminantIndex*  
 이미지 개체를 볼 광원의 광도 지정 합니다. 이 멤버는 다음 값 중 하나로 설정할 수 있습니다.  
  
- **ILLUMINANT_EQUAL_ENERGY**  
  
- **ILLUMINANT_A**  
  
- **ILLUMINANT_B**  
  
- **ILLUMINANT_C**  
  
- **ILLUMINANT_D50**  
  
- **ILLUMINANT_D55**  
  
- **ILLUMINANT_D65**  
  
- **ILLUMINANT_D75**  
  
- **ILLUMINANT_F2**  
  
- **ILLUMINANT_TURNGSTEN**  
  
- **ILLUMINANT_DAYLIGHT**  
  
- **ILLUMINANT_FLUORESCENT**  
  
- **ILLUMINANT_NTSC**  
  
 *caRedGamma*  
 소스 색의 빨간색 기본 데이터베이스에 n 번째 전원 감마 보정 값을 지정합니다. 2,500 65000 사이의 값 이어야 합니다. 값이 10, 000 없는 감마 보정을 의미합니다.  
  
 *caGreenGamma*  
 소스 색의 녹색 기본 데이터베이스에 n 번째 전원 감마 보정 값을 지정합니다. 2,500 65000 사이의 값 이어야 합니다. 값이 10, 000 없는 감마 보정을 의미합니다.  
  
 *caBlueGamma*  
 소스 색의 파란색 기본 데이터베이스에 n 번째 전원 감마 보정 값을 지정합니다. 2,500 65000 사이의 값 이어야 합니다. 값이 10, 000 없는 감마 보정을 의미합니다.  
  
 *caReferenceBlack*  
 원본 색상에 대 한 검은색 참조를 지정합니다. 이 보다 더 어두운 색은 검정으로 처리 됩니다. 값 0 4, 000 개 범위에 있어야 합니다.  
  
 *caReferenceWhite*  
 원본 색상에 대 한 흰색 참조를 지정합니다. 모든 색 보다 밝은 흰색으로 처리 됩니다. 10, 000으로 6, 000 까지의 범위에 값 이어야 합니다.  
  
 *caContrast*  
 원본 개체에 적용 될 수 대비 양을 지정 합니다. 값은 100에서 100 사이의 범위에 있어야 합니다. 값이 0 대비 조정이 없음을 의미합니다.  
  
 *caBrightness*  
 원본 개체에 적용 될 밝기를 지정 합니다. 값은 100에서 100 사이의 범위에 있어야 합니다. 값이 0 밝기 조정이 없음을 의미합니다.  
  
 *caColorfulness*  
 원본 개체에 적용 될 colorfulness 양을 지정 합니다. 값은 100에서 100 사이의 범위에 있어야 합니다. 값이 0 colorfulness 조정이 없음을 의미합니다.  
  
 *caRedGreenTint*  
 원본 개체에 적용 될 조정 빨간색 또는 녹색 tint 양을 지정 합니다. 값은 100에서 100 사이의 범위에 있어야 합니다. 양수는 빨간색으로 조정한 음수 녹색 쪽으로 조정 합니다. A 0 tint 조정이 없음을 의미합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)


