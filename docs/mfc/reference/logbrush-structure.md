---
title: "LOGBRUSH 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LOGBRUSH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOGBRUSH 구조체"
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# LOGBRUSH 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`LOGBRUSH` 구조체는 실제 브러쉬의 패턴과 스타일, 색상을 정의합니다.  이것은 [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) 와 [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) 함수들에 의해 사용됩니다.  
  
## 구문  
  
```  
  
      typedef struct tag LOGBRUSH { /* lb */  
   UINT lbStyle;  
   COLORREF lbColor;  
   LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### 매개 변수  
 `lbStyle`  
 브러시스타일을 지정합니다.  `lbStyle` 멤버는 다음 스타일중 하나여야 합니다.  
  
-   **BS\_DIBPATTERN** 패턴 브러시는 장치 독립적 비트맵 \(DIB\) 사양에 의해 정의됩니다.  만일 `lbStyle` 이 **BS\_DIBPATTERN**인 경우, **lbHatch** 멤버는 압축된 DIB에 대한 핸들을 포함합니다.  
  
-   **BS\_DIBPATTERNPT** 패턴 브러시는 장치 독립적 비트맵 \(DIB\) 사양에 의해 정의됩니다.  만일 `lbStyle` 가 **BS\_DIBPATTERNPT**인 경우, **lbHatch** 멤버는 압축된 DIB에 대한 포인터를 포함합니다.  
  
-   **BS\_HATCHED** 는 꾸며진 브러쉬입니다.  
  
-   **BS\_HOLLOW** 빈 브러시입니다.  
  
-   **BS\_NULL** 은 **BS\_HOLLOW** 와 같습니다.  
  
-   **BS\_PATTERN** 패턴 브러시는 비트맵 메모리에 의해 정의됩니다.  
  
-   **BS\_SOLID** 는 단색 브러시입니다.  
  
 `lbColor`  
 그려지는 브러쉬에 대한 색을 지정합니다.  만일 `lbStyle` 가 **BS\_HOLLOW** 이거나 **BS\_PATTERN** 스타일인 경우, **lbColor** 는 무시됩니다.  만일 `lbStyle` 가 **BS\_DIBPATTERN** 이거나 **BS\_DIBPATTERNBT**인 경우, [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) 구조체의 **bmiColors** 멤버들이 명시적으로 빨강, 녹색, 파랑\(RGB\) 값 또는 현재 실제 논리적 팔레트의 인덱스들을 나타내는지의 여부를 지정하는 **lbColor** 의 낮은 명령 단어입니다.  **lbColor** 멤버는 다음 값중 하나여야 합니다:  
  
-   **DIB\_PAL\_COLORS** 색상표는 현재 실현된 논리적 팔레트로 16비트 인덱스들의 배열로 구성되어 있습니다.  
  
-   **DIB\_RGB\_COLORS** 색상표는 리터럴 RGB 값을 포함합니다.  
  
 *lbHatch*  
 빗살 무늬 스타일을 지정합니다.  이 의미는 `lbStyle` 에 의해 정의된 브러시 스타일에 따라 달라집니다.  만일 `lbStyle` 이 **BS\_DIBPATTERN**인 경우, **lbHatch** 멤버는 압축된 DIB에 대한 핸들을 포함합니다.  만일 `lbStyle` 가 **BS\_DIBPATTERNPT**인 경우, **lbHatch** 멤버는 압축된 DIB에 대한 포인터를 포함합니다.  만일 `lbStyle` 이 **BS\_HATCHED**인 경우, **lbHatch** 멤버는 빗살 무늬를 만드는데 사용되는 선의 방향을 지정합니다.  이것은 다음 값 중 하나일 수 있습니다.  
  
-   `HS_BDIAGONAL` 는 윗쪽으로 45도, 왼쪽에서 오른쪽으로 빗살무늬를 그립니다.  
  
-   `HS_CROSS` 는 가로와 세로로 격자가 나타납니다.  
  
-   `HS_DIAGCROSS` 는 45도의 격자 무늬입니다.  
  
-   `HS_FDIAGONAL` 는 45도 아래로, 왼쪽에서 오른쪽으로 빗살 무늬를 그립니다.  
  
-   `HS_HORIZONTAL`는 가로로 빗살무늬를 만듭니다.  
  
-   `HS_VERTICAL` 의 경우 세로 빗살무늬입니다.  
  
 만일 `lbStyle` 가 **BS\_PATTERN**인 경우, **lbHatch** 이 패턴을 정의 하는 비트맵에 대한 핸들입니다.  만일 `lbStyle` 이 **BS\_SOLID** 이거나 **BS\_HOLLOW**인 경우, **lbHatch** 가 무시됩니다.  
  
## 설명  
 **lbColor** 이 빗살 무늬 브러시의 전경 색상을 설정하면, [CDC::SetBkMode](../Topic/CDC::SetBkMode.md) 와 [CDC::SetBkColor](../Topic/CDC::SetBkColor.md) 함수들은 배경색상을 제어합니다.  
  
## 요구 사항  
 **Header:** wingdi.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)