---
title: "XFORM 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: 11
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
ms.openlocfilehash: 2d23b3838f1e2dcabb2affb96fa6f18942581ff8
ms.lasthandoff: 02/24/2017

---
# <a name="xform-structure"></a>XFORM 구조체
`XFORM` 구조체 형식은 다음과 같습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## <a name="remarks"></a>주의  
 `XFORM` 구조 페이지 공간 변환 월드 공간을 지정 합니다. **eDx** 및 **eDy** 멤버 각각에 가로 및 세로 변환 구성 요소를 지정 합니다. 다음 표에서 작업에 따라 다른 멤버가 사용 하는 방법을 보여 줍니다.  
  
|작업|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|회전 각도의 코사인 값|회전 각도의 사인 값|회전 각도의 사인 한 음수 값|회전 각도의 코사인 값|  
|**크기 조정**|가로 크기 조정 구성 요소|Nothing|Nothing|세로 크기 조정 구성 요소|  
|**기울이기**|Nothing|가로 너비 대 높이 비율 상수|세로 너비 대 높이 비율 상수|Nothing|  
|**리플렉션**|가로 리플렉션 구성 요소|Nothing|Nothing|세로 리플렉션 구성 요소|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)


