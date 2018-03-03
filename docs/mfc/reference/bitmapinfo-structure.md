---
title: "BITMAPINFO 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BITMAPINFO
dev_langs:
- C++
helpviewer_keywords:
- BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9d704fec4a6ae0a95bd393b4a7fffa24884711e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bitmapinfo-structure"></a>BITMAPINFO 구조체
`BITMAPINFO` 차원 및 Windows 장치 독립적 비트맵 (DIB)에 대 한 색상 정보 구조를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagBITMAPINFO {  
    BITMAPINFOHEADER bmiHeader;  
    RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bmiHeader`  
 지정 된 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) 차원과 장치 독립적 비트맵의 색 형식에 대 한 정보가 포함 된 구조체입니다.  
  
 `bmiColors`  
 사용자 지정 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 또는 `DWORD` 비트맵에서 색을 정의 하는 데이터 형식입니다.  
  
## <a name="remarks"></a>설명  
 장치 독립적 비트맵 두 부분으로 구성 됩니다:는 `BITMAPINFO` 차원 및 비트맵의 색 및 비트맵의 픽셀을 지정 하는 바이트 배열을 설명 하는 구조입니다. 배열에 있는 비트 함께 압축 되는 있지만 각 검색 행에 종료 하기 위해 0으로 패딩해야는 `LONG` 경계입니다. 높이 양수인 경우 비트맵의 원점은 왼쪽 아래 모서리 있습니다. 높이 음수 이면 원점은 왼쪽 위 모서리 있습니다.  
  
 A *압축된 비트맵* 는 비트맵은 바이트 배열을 바로 뒤의 `BITMAPINFO` 구조입니다. 압축 된 비트맵 단일 포인터에 의해 참조 됩니다.  
  
 에 대 한 자세한 내용은 `BITMAPINFO` 구조체의 멤버에 대 한 적절 한 값이 고는 `BITMAPINFOHEADER` 및 `RGBQUAD` 구조는 Windows SDK 설명서의 다음 항목을 참조 합니다.  
  
- [BITMAPINFO 구조체](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
- [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) 구조  
  
- [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 구조  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)

