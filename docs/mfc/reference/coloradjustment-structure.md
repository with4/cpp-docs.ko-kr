---
title: COLORADJUSTMENT 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure [MFC]
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03c5346a59ea52ca6b2428652d5da69aacf6ea5b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849096"
---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT 구조체
`COLORADJUSTMENT` 구조는 Windows에서 사용 하는 색 조정 값을 정의 `StretchBlt` 하 고 `StretchDIBits` 함수 때는 `StretchBlt` 모드가 하프톤 합니다.  
  
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
 출력 이미지를 준비 하는 방식을 지정 합니다. 이 멤버는 NULL 또는 다음 값의 조합을 설정할 수 있습니다.  
  
- CA_NEGATIVE 원본 이미지의 음수를 표시 해야 함을 지정 합니다.  
  
- CA_LOG_FILTER 최종 출력 색의 밀도를 로그 하는 함수를 적용 해야 하는지 지정 합니다. 이렇게 하면 광도 낮은 경우 색상 대비를 늘어납니다.  
  
 *caIlluminantIndex*  
 이미지 개체를 볼 광원의 광도 지정 합니다. 이 멤버는 다음 값 중 하나로 설정할 수 있습니다.  
  
- ILLUMINANT_EQUAL_ENERGY  
  
- ILLUMINANT_A  
  
- ILLUMINANT_B  
  
- ILLUMINANT_C  
  
- ILLUMINANT_D50  
  
- ILLUMINANT_D55  
  
- ILLUMINANT_D65  
  
- ILLUMINANT_D75  
  
- ILLUMINANT_F2  
  
- ILLUMINANT_TURNGSTEN  
  
- ILLUMINANT_DAYLIGHT  
  
- ILLUMINANT_FLUORESCENT  
  
- ILLUMINANT_NTSC  
  
 *caRedGamma*  
 소스 색의 빨강 주의 n 번째 power 감마 보정 값을 지정합니다. 65000 2,500 사이의 값 이어야 합니다. 값이 10,000 없습니다 감마 보정을 의미합니다.  
  
 *caGreenGamma*  
 소스 색의 녹색 주의 n 번째 power 감마 보정 값을 지정합니다. 65000 2,500 사이의 값 이어야 합니다. 값이 10,000 없습니다 감마 보정을 의미합니다.  
  
 *caBlueGamma*  
 소스 색의 파랑 원색의 n 번째 power 감마 보정 값을 지정합니다. 65000 2,500 사이의 값 이어야 합니다. 값이 10,000 없습니다 감마 보정을 의미합니다.  
  
 *caReferenceBlack*  
 소스 색에 대 한 검정 참조를 지정합니다. 이보다 음영이 짙을 수록 된 모든 색은 검정으로 처리 됩니다. 값을 0에서 4,000 사이에 있어야 합니다.  
  
 *caReferenceWhite*  
 소스 색에 대 한 흰색 참조를 지정합니다. 이 보다 밝은 색은 흰색으로 처리 됩니다. 6,000 10,000 사이의 값 이어야 합니다.  
  
 *caContrast*  
 원본 개체에 적용할 대비 양을 지정 합니다. 값은 100부터 100 사이 여야 합니다. 값이 0 의미 없는 대비 조정 합니다.  
  
 *caBrightness*  
 원본 개체에 적용할 밝기를 지정 합니다. 값은 100부터 100 사이 여야 합니다. 값이 0 의미 없는 밝기 조정 합니다.  
  
 *caColorfulness*  
 원본 개체에 적용할 colorfulness 양을 지정 합니다. 값은 100부터 100 사이 여야 합니다. 값이 0 의미 없는 colorfulness 조정 합니다.  
  
 *caRedGreenTint*  
 원본 개체에 적용할 빨간색 또는 녹색 색조 조정의 양을 지정 합니다. 값은 100부터 100 사이 여야 합니다. 양수는 빨간색으로 조정한 음수 녹색으로 조정 합니다. 0 없습니다 tint 조정을 의미합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)


