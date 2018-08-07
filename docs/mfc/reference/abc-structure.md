---
title: ABC 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c9aac181edb12df8904a2bc6d891d59c0067ecc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339321"
---
# <a name="abc-structure"></a>ABC 구조체
`ABC` 구조 트루타입 글꼴의 문자 너비를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *abcA*  
 문자는 간격을 지정합니다. 간격에는 문자 모양 그리기 전에 현재 위치에 추가할 거리입니다.  
  
 *abcB*  
 문자 B 간격을 지정합니다. B 간격에는 문자 모양이 그려지는 부분의 너비입니다.  
  
 *abcC*  
 문자 C 간격을 지정합니다. C 간격에는 문자 모양의 오른쪽에 공백 수 있도록 현재 위치에 추가할 거리입니다.  
  
## <a name="remarks"></a>설명  
 문자의 총 너비는 A, B 및 C 공간의 합계입니다. A 또는 C 공간 underhangs 또는 돌출부 나타내기 위해 음수일 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** wingdi.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


