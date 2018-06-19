---
title: 가변 매개 변수 형식 상수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
dev_langs:
- C++
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13820ff4fb07c3743f36ba3ebe33ee56a3a79c7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379862"
---
# <a name="variant-parameter-type-constants"></a>가변 매개 변수 형식 상수
이 항목에는 OLE 컨트롤 클래스 Microsoft Foundation Class 라이브러리를 사용 하도록 설계 가변 매개 변수 유형을 나타내는 새 상수 보여 줍니다.  
  
 다음은 클래스 상수의 목록입니다.  
  
##  <a name="_mfc_variant_data_constants"></a> 가변 데이터 상수  
  
-   **VTS_COLOR** RGB 색상 값을 나타내는 데 사용 되는 32 비트 정수입니다.  
  
-   **VTS_FONT** 에 대 한 포인터는 **IFontDisp** OLE 글꼴 개체의 인터페이스입니다.  
  
-   **VTS_HANDLE** Windows 핸들 값입니다.  
  
-   **VTS_PICTURE** 에 대 한 포인터는 `IPictureDisp` OLE 그림 개체의 인터페이스입니다.  
  
-   **VTS_OPTEXCLUSIVE** 라디오 단추와 같이 컨트롤의 그룹에 사용 하려고 하는 컨트롤에 사용 되는 16 비트 값입니다. 이 형식은 지시 컨테이너의 컨트롤 하나는 그룹에는 **TRUE** , 다른 모든 길어야 **FALSE**합니다.  
  
-   **VTS_TRISTATE** 확인란 (선택한, 캐시, 사용할 수 없음) 3 가지 값 중 하나를 예를 들어 가질 수 있는 속성에 사용 되는 16 비트 부호 있는 정수입니다.  
  
-   **VTS_XPOS_HIMETRIC** x 축 따라 위치를 나타내는 데 사용 되는 32 비트 부호 없는 정수 **HIMETRIC** 단위입니다.  
  
-   **VTS_YPOS_HIMETRIC** 에 y 축 위치를 나타내는 데 사용 되는 32 비트 부호 없는 정수 **HIMETRIC** 단위입니다.  
  
-   **VTS_XPOS_PIXELS** x 축 따라 위치를 픽셀 단위로 나타내는 데 사용 되는 32 비트 부호 없는 정수입니다.  
  
-   **VTS_YPOS_PIXELS** y 축 위치를 픽셀 단위로 나타내는 데 사용 되는 32 비트 부호 없는 정수입니다.  
  
-   **VTS_XSIZE_PIXELS** 를 픽셀 단위로 화면 개체의 너비를 나타내는 데 사용 하는 32 비트 부호 없는 정수입니다.  
  
-   **VTS_YSIZE_PIXELS** 를 픽셀 단위로 화면 개체의 높이 나타내는 데 사용 하는 32 비트 부호 없는 정수입니다.  
  
-   **VTS_XSIZE_HIMETRIC** 32 비트 부호 없는 정수에는 화면 개체의 너비를 나타내는 데 **HIMETRIC** 단위입니다.  
  
-   **VTS_YSIZE_HIMETRIC** 32 비트 부호 없는 정수에는 화면 개체의 높이 나타내는 데 **HIMETRIC** 단위입니다.  
  
    > [!NOTE]
    >  추가 variant 상수를 모든 variant 형식에 대해 정의 된 **VTS_FONT** 및 **VTS_PICTURE**, variant 데이터 co에 대 한 포인터를 제공 하는 nstant 합니다. 이러한 상수를 사용 하 여 라고는 **VTS_P** `constantname` 규칙입니다. 예를 들어 **VTS_PCOLOR** 에 대 한 포인터는 **VTS_COLOR** 상수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
