---
title: "RGNDATA 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RGNDATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RGNDATA 구조체"
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# RGNDATA 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `RGNDATA` 구조는 헤더 및 영역을 구성 하는 사각형의 배열을 포함 합니다. 이 사각형을 정렬된 하 여 위에서 아래로 왼쪽에서 오른쪽으로 중첩 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
 
    typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rdh*  
 지정 된 [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) 구조입니다. (이 구조에 대 한 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].) 이 구조체의 멤버는 영역의 형식을 (사각형 또는 인지 사다리꼴), 영역, 사각형 구조를 포함 하는 버퍼의 크기를 구성 하는 사각형의 수를 지정 하 고 등.  
  
 `Buffer`  
 포함 하는 임의 크기의 버퍼를 지정 합니다.는 [RECT](../../mfc/reference/rect-structure1.md) 지역을 구성 하는 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#CreateFromData)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#GetRegionData)

