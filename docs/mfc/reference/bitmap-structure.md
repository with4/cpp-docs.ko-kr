---
title: "BITMAP 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BITMAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAP 구조체"
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BITMAP 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**비트맵** 구조체는 논리적 비트맵의 높이, 넓이, 색 형식과 비트 값을 정의합니다**.**  
  
## 구문  
  
```  
  
      typedef struct tagBITMAP {  /* bm */  
   int bmType;  
   int bmWidth;  
   int bmHeight;  
   int bmWidthBytes;  
   BYTE bmPlanes;  
   BYTE bmBitsPixel;  
   LPVOID bmBits;  
} BITMAP;  
```  
  
#### 매개 변수  
 *bmType*  
 비트맵의 형식을 지정합니다.  논리적 비트맵의 경우 이 멤버는 0 이어야 합니다.  
  
 *bmWidth*  
 비트맵의 너비를 픽셀 단위로 지정 합니다.  이 값은 0보다 커야 합니다.  
  
 *bmHeight*  
 래스터 줄 단위로 비트맵의 높이를 지정합니다.  이 값은 0보다 커야 합니다.  
  
 *bmWidthBytes*  
 각 래스터 줄 단위로 바이트 수를 지정합니다.  그래픽 장치 인터페이스 \(GDI\)가 비트맵의 비트 값이 정수 값\(2 바이트\)의 배열을 형성한다고 가정하므로 이 값은 반드시 짝수여야 합니다.  즉, **bmWidthBytes** \*8은 반드시 **bmWidth** 멤버가 **bmBitsPixel** 멤버와 곱해질 때 얻어진 값과 같거나 더 큰 16의 배수여야 합니다.  
  
 *bmPlanes*  
 비트맵내의 색 평면의 수를 지정합니다.  
  
 *bmBitsPixel*  
 픽셀을 정의 하는데 필요한 각 평면에 인접한 색상 비트 수를 지정 합니다.  
  
 *bmBits*  
 비트맵에 대한 비트 값의 위치를 가리킵니다.   **bmBits** 멤버는 1 바이트 값의 배열에 대한 긴 포인터여야 합니다.  
  
## 설명  
 현재 사용 되는 비트맵 형식에는 흑백과 컬러가 있습니다.  흑백 비트맵은 1비트, 1 평면 형식을 사용합니다.  각 스캔은 16의 배수입니다.  
  
 높이 *n* 의 비트맵에 대해 스캔은 다음과 같이 구성됩니다.  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 흑백 장치에서 픽셀은 검정색이거나 흰색입니다.  비트맵의 해당 비트가 1 이면 픽셀은 \(흰색\)으로 켜집니다.  비트맵의 해당 비트가 0 이면 픽셀은 \(검정\)으로 켜집니다.  
  
 모든 장치는 [CDC::GetDeviceCaps](../Topic/CDC::GetDeviceCaps.md) 멤버 함수의 **RASTERCAPS** 인덱스에 설정된 **RC\_BITBLT** 비트를 가진 비트맵을 지원합니다.  
  
 각 장치는 자체의 고유한 색 형식을 가집니다.  비트맵을 한 장치에서 다른 장치로 전송하기 위해서 [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) 와 [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) Windows 함수를 사용하십시오.  
  
## 요구 사항  
 **Header:** wingdi.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)